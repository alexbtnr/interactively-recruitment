<template>
  <header class="header">
    <div class="container">
      <h1 class="logo">Outperf<i class="las la-atom"></i>rm</h1>
      <nav id="nav">
        <router-link to="/">Home</router-link>
        <router-link to="/team">Team</router-link>
        <router-link class="smth" to="/about">About</router-link>
        <a href="#footer">Contact</a>
      </nav>
    </div>
  </header>
</template>

<script>
  export default {
    name: "Header",
  };
</script>

<style scoped>
  header.header {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 15vh;
    z-index: 2;
  }

  i.las {
    transition: all 1s ease;
  }

  h1.logo:hover i.las {
    transform: rotate(360deg);
  }

  .container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 100%;
  }

  nav#nav {
    width: 40%;
    display: flex;
    justify-content: space-around;
  }

  nav#nav a {
    font-size: 1.2rem;
    border-bottom: 1px solid transparent;
    transition: all 0.5s ease;
  }

  #nav a.router-link-exact-active::after {
    content: "";
    transform: scaleX(1);
    border-bottom: solid 2px #000;
  }

  nav#nav a::after {
    display: block;
    content: "";
    border-bottom: solid 2px #000;
    transform: scaleX(0);
    transition: all 250ms ease-in-out;
  }

  nav#nav a:hover::after {
    transform: scaleX(1);
  }
</style>
