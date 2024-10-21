<template>
  <div style="height: 100%; background-color: #141414;">
    <Header></Header>
    <main class="container">
      <div class="main-div">
        My name is Miguel, I am a programmer and a space lover
      </div>
    </main>
  </div>
  
</template>

<script setup>
import Header from '@/components/HeaderPage.vue';
  //
</script>

<style scoped>
  .container {
    display: flex;
    justify-content: center;
    width: 100%;
    color: #FFF;
  }
  .main-div {
    width: 300px;
    height: 500px;
    margin-top: 200px;
    font-size: 30px;
  }
</style>

