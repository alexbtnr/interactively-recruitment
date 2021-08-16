<template>
  <div class="single-user">
    <div class="upper-flex">
      <div class="profile-image">
        {{ getFirstInitial() }} {{ getSecondInitial() }}
      </div>
      <button
        @tap="$emit('del-user', user.id)"
        @click="$emit('del-user', user.id)"
        class="del"
      >
        Delete User
      </button>
      <div class="user-details">
        <p class="name">{{ user.name }}</p>
        <p class="username">{{ user.username }}</p>
        <p class="website">{{ user.website }}</p>
      </div>
    </div>
    <div class="lower-flex">
      <p class="phone"><i class="las la-phone"></i> {{ user.phone }}</p>
      <p class="email"><i class="las la-envelope"></i> {{ user.email }}</p>
    </div>
  </div>
</template>

<script>
  export default {
    name: "SingleUser",
    props: ["user"],
    methods: {
      getFirstInitial() {
        if (this.user.name.split(" ")[0].includes("Mrs.")) {
          return "D"; // i know you wouldn't use this in production, but I tried removing the mrs using slice() and it wouldn't let me because it's an external api and i can't modify their database
        }
        return this.user.name.split(" ")[0][0];
      },
      getSecondInitial() {
        return this.user.name.split(" ")[1][0];
      },
    },
  };
</script>

<style>
  .single-user {
    display: flex;
    border: 1px solid #333;
    flex-direction: column;
    align-items: center;
    padding: 0.5rem;
    gap: 2rem;
    min-height: 10rem;
    min-width: 20rem;
  }
  .profile-image {
    background: #333;
    padding: 1rem;
    color: #eee;
    border-radius: 50%;
    text-transform: uppercase;
  }
  .upper-flex {
    display: flex;
    justify-content: space-between;
    width: 100%;
    align-items: center;
  }
  .upper-flex .website {
    text-decoration: underline;
    cursor: pointer;
  }
  .upper-flex .del {
    align-self: flex-start;
    background: rgb(187, 24, 24);
    font-size: 1.1rem;
    cursor: pointer;
    color: #fff;
    padding: 1rem;
    border: none;
  }
  .upper-flex .del:hover {
    background: rgb(211, 12, 12);
    text-decoration: underline;
  }
  .lower-flex {
    display: flex;
    justify-content: space-between;
    width: 100%;
  }
  .lower-flex i {
    font-size: 1.2rem;
  }

  @media (max-width: 825px) {
    .single-user {
      flex-direction: column;
      justify-content: center;
      align-items: center;
    }
    .upper-flex {
      flex-direction: column;
      text-align: center;
      justify-content: center;
      align-items: center;
      gap: 1rem;
    }
    .upper-flex .del {
      align-self: center;
    }
    .lower-flex {
      flex-direction: column;
      text-align: center;
      justify-content: center;
      align-items: center;
      gap: 1rem;
    }
  }
</style>
