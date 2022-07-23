<script setup lang="ts">
import { ref } from "vue";
const inputTweet: string = "";

const tweets: ref([])

const postTweet = () => {};
</script>

<template>
  <div class="container">
    <h1>Twitter</h1>
    <div class="form-container">
      <input v-model="inputTweet" />
      <button @click="postTweet(inputTweet)">POST</button>
    </div>
    <div class="tweet-container">
      <ul>
        <li v-for="tweet in tweets" class="tweet-list" :key="tweet.id">
          {{ tweet.description }}
        </li>
      </ul>
    </div>
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
.tweet-list {
  list-style: none;
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