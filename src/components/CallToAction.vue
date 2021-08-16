<template>
  <main class="main">
    <div class="action">
      <h1 class="title">
        Make Your Dream Come True
      </h1>
      <button @mouseenter="enterImage" @mouseleave="exitImage" class="btn">
        <router-link to="/team"><span>Meet The Team</span></router-link>

        <i class="las la-angle-double-right la-2x"></i>
      </button>
    </div>
    <div class="team">
      <p class="lead">
        A reliable team to make your website look beautiful and professional.
      </p>
      <img :class="{ entered: show }" src="../assets/team.jpg" alt="team" />
    </div>
  </main>
</template>

<script>
  export default {
    name: "CallToAction",
    data() {
      return {
        show: false,
      };
    },
    methods: {
      enterImage() {
        this.show = true;
      },
      exitImage() {
        this.show = false;
      },
    },
  };
</script>

<style>
  main.main {
    height: 100vh;
    display: flex;
    justify-content: space-between;
    align-items: center;
    overflow-x: hidden;
  }

  div.action {
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: flex-start;
    gap: 2rem;
  }

  h1.title {
    font-size: 4.5rem;
  }

  button.btn {
    padding: 1rem 2rem;
    border: 2px solid #000;
    font-size: 1.2rem;
    background: transparent;
    cursor: pointer;
    display: flex;
    align-items: center;
    transition: all 0.5s ease;
  }

  button.btn i {
    transition: all 0.5s ease;
  }

  button.btn:hover {
    color: #abcffd;
    background: #000;
  }

  button.btn:hover i {
    transform: translateX(10px);
  }

  div.team {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 50%;
    gap: 2rem;
  }

  div.team img {
    object-fit: cover;
    object-position: center center;
    border-radius: 50%;
    transform: translateX(100%);
    opacity: 0;
    transition: all 0.5s ease;
  }

  div.team img.entered {
    opacity: 1;
    transform: translateX(0);
  }

  p.lead {
    font-size: 1.4rem;
    align-self: center;
  }

  @media (max-width: 825px) {
    main.main {
      padding-top: 15vh;
      flex-direction: column;
      justify-content: center;
      align-items: center;
    }
    div.action {
      height: 50%;
    }
    div.action h1 {
      font-size: 2rem;
      text-align: center;
    }
    div.action button.btn {
      margin: 0 auto;
    }
    div.team img {
      display: none;
    }
    div.team {
      width: 100%;
    }
    div.team p.lead {
      margin: 0 auto;
      text-align: center;
    }
  }
</style>
