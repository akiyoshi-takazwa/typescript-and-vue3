<script setup lang="ts">
</script>

<template>
  <div class="container">
    <h1>Twitter</h1>
    <div class="form-container">
      <input />
      <button class>POST</button>
    </div>
    <div class="tweet-container"></div>
  </div>
</template>


<style scoped>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.form-container {
  display: flex;
  flex-direction: column;
  margin: 0 auto;
  align-items: center;
  background-color: aliceblue;
  padding: 24px 0;
  width: 60%;
  margin-bottom: 12px;
  border-radius: 4px;
}
button {
  margin-top: 10px;
  color: #fff;
  font-weight: bold;
  background-color: #68c9c9;
  border-radius: 2px;
  border: none;
  height: 20px;
  width: 60px;
}
</style>