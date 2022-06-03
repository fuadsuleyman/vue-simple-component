 <template>
  <h2>My Friends</h2>
  <section>
    <ul>
      <friend-contact></friend-contact>
      <friend-contact></friend-contact>
    </ul>
  </section>
</template>

<script>

export default {
  data() {
    return {
      FriendContact: [
        {
          id: "manuel",
          name: "Manuel Lorenz",
          phone: "+994 50 270 25 69",
          email: "manuel@localhost.com",
        },
        {
          id: "julie",
          name: "Julie Fazzy",
          phone: "+994 55 270 25 69",
          email: "julie@localhost.com",
        },
      ],
    };
  },
};
</script>