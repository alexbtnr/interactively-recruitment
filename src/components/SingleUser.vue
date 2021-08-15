<template>
  <div class="single-user">
    <!-- <div class="profile-image">a b</div>
    <div class="user-details">
      <div class="upper-flex">
        <div class="name-website">
          <p class="name">name <span class="username">username</span></p>
          <p class="website">website</p>
        </div>
        <div class="city-company">
          <p class="city">city</p>
          <p class="company">company</p>
        </div>
      </div>
      <div class="lower-flex">
        <div class="phone">phone</div>
        <div class="email">email</div>
      </div>
    </div> -->

    <div class="upper-flex">
      <div class="profile-image">a b</div>
      <div class="user-details">
        <p class="name">{{ user.name }}</p>
        <p class="username">{{ user.username }}</p>
        <p class="website">{{ user.website }}</p>
      </div>
    </div>
    <!-- <div class="middle-flex">
      <p class="company-name">Company:</p>
      <p class="phone-nr">Phone:</p>
      <p class="email-address">Email:</p>
    </div> -->
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
  };
</script>

<style>
  .single-user {
    display: flex;
    border: 1px solid black;
    /* justify-content: space-between;
    
    align-items: center; */
    flex-direction: column;
    align-items: center;
    padding: 0.5rem;
    /* text-align: center; */
    gap: 2rem;
    min-height: 10rem;
    min-width: 20rem;
  }
  .profile-image {
    background: #333;
    padding: 0.5rem;
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
  .lower-flex {
    display: flex;
    justify-content: space-between;
    width: 100%;
  }
  .lower-flex i {
    font-size: 1.2rem;
  }
</style>
