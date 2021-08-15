<template>
  <main class="main-team">
    <TeamContainer v-bind:users="users" />
    <Footer />
  </main>
</template>

<script>
  import Footer from "../components/Footer.vue";
  import TeamContainer from "../components/TeamContainer.vue";

  import axios from "axios";

  export default {
    name: "Team",
    components: {
      Footer,
      TeamContainer,
    },
    data() {
      return {
        users: [],
      };
    },
    created() {
      axios
        .get("https://jsonplaceholder.typicode.com/users")
        .then((res) => (this.users = res.data))
        .catch((err) => console.log(err));
    },
  };
</script>

<style></style>
