<template>
  <li>
    <h2>{{ name }} {{ isFavorite ? "(Favotite)" : "" }}</h2>
    <button @click="toggleDetails">
      {{ detailsAreVisible ? "Hide" : "Show" }} Details
    </button>
    <button @click="toggleFavorite">
      {{ isFavorite ? "Hide" : "Show" }} Favorite
    </button>
    <ul v-if="detailsAreVisible">
      <li><strong>Phone</strong> {{ phoneNumber }}</li>
      <li><strong>Email</strong> {{ emailAddress }}</li>
    </ul>
    <button @click="$emit('delete', id)">Delete</button>
  </li>
</template>

<script>
export default {
  //   props: ["name", "phoneNumber", "emailAddress"],
  props: {
    id: {
      type: String,
      required: true,
    },
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
  // this below something as documantation, we provide information about emited methods
  // first is simple version, second extended version
  emits: ["toggle-favorite", "delete"],
  // emits: {
  //   'toggle-favorite': function(id) {
  //     if (id){
  //       return true;
  //     } else {
  //       console.warn("Id is missing!")
  //       return false;
  //     }
  //   }
  // },
  data() {
    return {
      detailsAreVisible: false,
    };
  },
  methods: {
    toggleDetails() {
      this.detailsAreVisible = !this.detailsAreVisible;
    },
    toggleFavorite() {
      this.$emit("toggle-favorite", this.id);
    },
  },
};
</script>