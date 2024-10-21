<script>
// import { ref } from 'vue';
export default {
  data() {
    return {
    };
  },
  methods: {
  }
}
</script>

<template>
  <header>
    <ul class="header">
      <img class="logo-img"  src="../assets/logo2.png"/>
      <div style="display: flex; gap: 30px;">
        <li class="outside-items"><RouterLink  class="header-items" to="/homePage">Home</RouterLink ></li>
        <li class="outside-items"><RouterLink class="header-items" to="/postPage">Posts</RouterLink></li>
        <li class="outside-items"><RouterLink class="header-items" to="/aboutMePage">About me</RouterLink></li>
      </div>
    </ul>
  </header>
</template>

<style scoped>
  .header {
    display: flex;
    list-style: none;
    align-items: center;
    justify-content: space-around;
    font-size: 20px;
    background-color: #141414;
    color: #fff;
  }
  .logo-img {
    width: 300px;
    cursor: pointer;
  }
  .header-items {
    text-decoration: none;
    color: #fff;
    padding: 10px;
    border-radius: 3px;
  }
  .header-items:hover {
    cursor: pointer;
    transition: .2s;
    background-color: #FFC300;
    color: #141414;
  }
</style>