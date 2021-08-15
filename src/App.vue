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
  /* #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
} */

  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
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
