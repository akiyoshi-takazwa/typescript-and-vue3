<script setup lang="ts">
import {defineEmits, defineProps} from "vue";

type Tweet = {
  id: number,
  description: string
}

type Props = {
  tweets: Tweet[],
  deleteTweet: (id: number) => void,
}
defineProps<Props>()
</script>

<template>
  <li v-for="tweet in tweets" class="tweet-list" :key="tweet.id">
    <span>{{ tweet.description }}</span>
    <button @click="deleteTweet(tweet.id)" class="tweet-list_button">削除</button>
  </li>
</template>

<style scoped>
.tweet-list {
  list-style: none;
  display: flex;
  background-color: thistle;
  justify-content: space-between;
  margin-bottom: 20px;
  padding: 4px 0 4px 10px;
  width: 500px;
}

</style>