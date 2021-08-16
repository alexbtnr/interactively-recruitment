<template>
  <div class="home">
    <div class="container">
      <CallToAction />
    </div>
    <Footer />
  </div>
</template>

<script>
  import CallToAction from "../components/CallToAction.vue";
  import Footer from "../components/Footer.vue";
  export default {
    name: "Home",
    components: {
      CallToAction,
      Footer,
    },
    created() {
      document.title = "Outperform | HomePage";
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
  @media (max-width: 768px) {
    .home {
    }
  }
</style>
