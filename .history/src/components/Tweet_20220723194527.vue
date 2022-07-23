<script setup lang="ts">
import { ref } from "vue";
const inputTweet: string = "";

const tweets = ref([
  {
    id: 1,
    description: "",
  },
]);

const inputDescription = ref<string>("");

const postTweet = () => {
  const tweet = {
    id: Math.random(),
    // input 系はvalue属性からデータを取得するんので、.valueが必要
    description: inputDescription.value,
  };
  tweets.value.push(tweet);
};

const deleteDescription = (id: number) => {
  console.log("deleteDescription", id);
  // リアクティブになっているのでvalue値を変更するだけで変わる
  tweets.value = tweets.value.filter((tweet) => tweet.id !== id);
};
</script>

<template>
  <div class="container">
    <h1>Twitter</h1>
    <div class="form-container">
      <input v-model="inputDescription" />
      <button @click="postTweet()">POST</button>
    </div>
    <div class="tweet-container">
        <div v-if="tweets.length > 0"></div>
      <ul>
        <li v-for="tweet in tweets" class="tweet-list" :key="tweet.id">
          {{ tweet.description }}
          <button @click="deleteDescription(tweet.id)">削除</button>
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
  display: flex;
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