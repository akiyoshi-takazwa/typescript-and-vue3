<script setup lang="ts">
</script>

<template>
  <div class="container">
    <h1>Twitter</h1>
    <div>
      <input />
      <button>POST</button>
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
button{
    color: #fff;
    font-weight: bold;
    background-color: #68c9c9;
    border-radius: 2px;
    border: none;
}
</style>