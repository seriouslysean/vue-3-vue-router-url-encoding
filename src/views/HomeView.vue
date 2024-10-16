<script setup lang="ts">
import { useRouter } from 'vue-router';

const router = useRouter();

const wordList: string[] = ['foo', 'bar', 'baz'];

function getRandomWord(): string {
  const randomIndex: string = Math.floor(Math.random() * wordList.length);
  return wordList[randomIndex];
}

function getRandomNumber(): number {
  return Math.floor(Math.random() * 100) + 1;
}

function onClick() {
  const randomWord = getRandomWord();
  const randomNumber = getRandomNumber();
  router.push({ query: { word: `${randomWord} ${randomNumber}` } });
}
</script>

<template>
  <div>
    <h2>Home View</h2>
    <button @click="onClick">Click to Set Query Param</button>
  </div>
</template>
