<template>
  <li>
    <h2>{{ name }} {{ frienIsFavorite ? "(Favotite)" : "" }}</h2>
    <button @click="toggleDetails">
      {{ detailsAreVisible ? "Hide" : "Show" }} Details
    </button>
    <button @click="toggleFavorite">
      {{ frienIsFavorite ? "Hide" : "Show" }} Favorite
    </button>
    <ul v-if="detailsAreVisible">
      <li><strong>Phone</strong> {{ phoneNumber }}</li>
      <li><strong>Email</strong> {{ emailAddress }}</li>
    </ul>
  </li>
</template>

<script>
export default {
  //   props: ["name", "phoneNumber", "emailAddress"],
  props: {
    name: {
      type: String,
      required: true,
    },
    phoneNumber: {
      type: String,
      required: true,
    },
    emailAddress: {
      type: String,
      required: true,
    },
    isFavorite: {
      type: Boolean,
      required: false,
      default: false,
      // validator: function (value) {
      //   return value === "0" || value === "1";
      // },
    },
  },
  data() {
    return {
      detailsAreVisible: false,
      frienIsFavorite: this.isFavorite
    };
  },
  methods: {
    toggleDetails() {
      this.detailsAreVisible = !this.detailsAreVisible;
    },
    toggleFavorite(){
      this.frienIsFavorite = !this.frienIsFavorite
    }
  },
};
</script>