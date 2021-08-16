<template>
  <div id="app">
    <!-- <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div> -->
    <Header />
    <router-view />
  </div>
</template>

<script>
  import Header from "./components/Header.vue";
  export default {
    name: "App",
    components: {
      Header,
    },
  };
</script>

<style>
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }

  html {
    scroll-behavior: smooth;
  }

  body {
    font-family: Roboto, Arial, Helvetica, sans-serif;
    line-height: 1.4;
  }

  a {
    color: #000;
    text-decoration: none;
  }

  .container {
    width: 80%;
    margin: 0 auto;
  }

  img {
    width: 100%;
  }
</style>
