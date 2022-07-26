<template>
  <div class="form-container">
    <input v-model="inputDescription" />
    <button class="form-container_button" @click="postTweet">POST</button>
  </div>
</template>

<script setup lang="ts">
import {defineEmits, ref} from "vue";

const inputDescription = ref<string>('');

// 子供から親へデータを渡す
const emit = defineEmits(['post-tweet'])
const postTweet = () => {
  emit('post-tweet', inputDescription.value, 'wwww')
};

</script>

<style scoped>
.form-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  background-color: aliceblue;
  padding: 24px 0;
  width: 60%;
  margin-bottom: 12px;
  border-radius: 4px;
}


.form-container_button{
  width: 80px;
  background-color: lightskyblue;
  color: #fff;
  padding: 2px 10px;
  margin-top: 5px;
}

</style>