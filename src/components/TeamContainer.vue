<template>
  <div class="people-background">
    <div class="team-container">
      <div class="container">
        <div class="sort-buttons">
          <button @click="sortAsc()">
            <span> Sort Users Ascending</span>
            <i class="las la-angle-double-up la-2x"></i>
          </button>
          <button @click="sortDesc()">
            <span> Sort Users Descending</span>
            <i class="las la-angle-double-down la-2x"></i>
          </button>
        </div>
        <div v-if="sorted" class="single-user-container">
          <div v-bind:key="user.id" v-for="user in usersSorted">
            <SingleUser
              v-bind:user="user"
              v-on:del-user="$emit('del-user', user.id)"
            />
          </div>
        </div>
        <div v-else class="single-user-container">
          <div v-bind:key="user.id" v-for="user in users">
            <SingleUser
              v-bind:user="user"
              v-on:del-user="$emit('del-user', user.id)"
            />
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
    data() {
      return {
        usersSorted: this.users,
        sorted: false,
      };
    },
    components: {
      SingleUser,
    },
    methods: {
      sortAsc() {
        const sortedUsers = this.users.slice().sort((a, b) => {
          return a.name > b.name ? 1 : -1;
        });

        this.usersSorted = sortedUsers;
        this.sorted = true;
      },
      sortDesc() {
        const sortedUsers = this.users.slice().sort((a, b) => {
          return a.name < b.name ? 1 : -1;
        });

        this.usersSorted = sortedUsers;
        this.sorted = true;
      },
    },
  };
</script>

<style>
  .people-background {
    background-image: linear-gradient(120deg, #a1c4fd 0%, #c2e9fb 100%);
    min-height: 100vh;
  }
  .team-container {
    padding: 10rem 0;
  }

  .single-user-container {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 1rem;
  }

  .container .sort-buttons {
    display: flex;
    width: 100%;
    justify-content: space-between;
    margin-bottom: 2rem;
  }

  .container .sort-buttons button {
    padding: 1rem 2rem;
    border: 2px solid #000;
    font-size: 1.2rem;
    background: transparent;
    cursor: pointer;
    display: flex;
    align-items: center;
    transition: all 0.5s ease;
    display: flex;
    gap: 0.5rem;
  }

  .container .sort-buttons button i {
    transition: all 0.5s ease;
  }

  .container .sort-buttons button:hover {
    color: #abcffd;
    background: #000;
  }

  .container .sort-buttons button:hover i.la-angle-double-up {
    transform: translateY(-10px);
  }
  .container .sort-buttons button:hover i.la-angle-double-down {
    transform: translateY(10px);
  }

  @media (max-width: 768px) {
    .single-user-container {
      display: grid;
      grid-template-columns: 1fr;
      gap: 1rem;
    }

    .container .sort-buttons {
      flex-direction: column;
      width: 16rem;
      gap: 1rem;
      margin: 0 auto 2rem;
    }
    .container .sort-buttons button {
      border: 2px solid #000;
      font-size: 1.2rem;
      background: transparent;
      cursor: pointer;
      display: flex;
      align-items: center;
      transition: all 0.5s ease;
      display: flex;
    }
  }
</style>
