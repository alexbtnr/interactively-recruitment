<template>
  <div class="people-background">
    <div class="team-container">
      <div class="container">
        <div class="single-user-container">
          <div v-bind:key="user.id" v-for="user in users">
            <SingleUser v-bind:user="user" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  import SingleUser from "./SingleUser.vue";
  export default {
    name: "TeamContainer",
    props: ["users"],
    components: {
      SingleUser,
    },
  };
</script>

<style>
  .people-background {
    background-image: linear-gradient(120deg, #a1c4fd 0%, #c2e9fb 100%);
  }
  .team-container {
    padding: 10rem 0;
  }

  .single-user-container {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 1rem;
  }
</style>
