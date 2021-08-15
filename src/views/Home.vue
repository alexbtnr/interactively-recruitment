<template>
  <div class="home">
    <div class="container">
      <CallToAction />
    </div>
  </div>
</template>

<script>
  import CallToAction from "../components/CallToAction.vue";
  export default {
    name: "Home",
    components: {
      CallToAction,
    },
  };
</script>

<style scoped>
  .home {
    position: relative;
    height: 100vh;
    /* background: url("../assets/pexels-eva-elijas-7661135.jpg") top center/cover
      no-repeat; */
    background-image: linear-gradient(120deg, #a1c4fd 0%, #c2e9fb 100%);
  }
</style>
