<template>
  <div class="about">
    <div class="about-background">
      <div class="container">
        <h1>This is an about page that is still in construction.</h1>
      </div>
    </div>
    <Footer />
  </div>
</template>

<script>
  import Footer from "../components/Footer.vue";
  export default {
    name: "About",
    components: {
      Footer,
    },
  };
</script>

<style>
  .about-background {
    background-image: linear-gradient(120deg, #a1c4fd 0%, #c2e9fb 100%);
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .about .container {
    display: flex;
    justify-content: center;
    align-items: center;
  }
</style>
