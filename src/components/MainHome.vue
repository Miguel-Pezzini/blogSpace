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
  <main class="main">
    <div class="main-div">
      <p class="main-text">Welcome to my blog! <br/><RouterLink to="/posts" class="blog-title">BlogSpace</RouterLink></p>
    </div>
  </main>
</template>

<style scoped>
  .main {
    color: #FFF;
    height: calc(100% - 200px);
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .main-text {
    font-size: 40px;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  .blog-title {
    color: #FFC300;
    font-size: 60px;
    text-decoration: none;
  }
  .blog-title:hover {
    transition: .2s;
    scale: 1.05;
    cursor: pointer;
  }
</style>