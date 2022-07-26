<script setup lang="ts">
import TweetPostForm from "./TweetPostForm.vue";
import TweetList from "./TweetList.vue";
import {ref} from "vue";


const inputDescription = ref(<string>(''));
const tweets = ref([{id: 0, description: 'Hello'}, {id:1, description: 'GoodBye'}])


const postTweet = (description: string, abc: string) => {
  console.log(abc)
  const tweet = { id: Math.random(), description: description};
  tweets.value.push(tweet);
};

const deleteTweet = (id: number) => {
  tweets.value = tweets.value.filter((t) => t.id !== id);
};
</script>

<template>
  <div class="container">
    <h1>Twitter</h1>
    <TweetPostForm @post-tweet="postTweet"/>
    <div class="tweet-container">
      <ul v-if="tweets.length > 0">
        <TweetList :tweets="tweets" :delete-tweet="deleteTweet"/>
      </ul>
      <p v-else>データがありません</p>
    </div>
  </div>
</template>


<style scoped>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>