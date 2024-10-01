<script setup>
import { ref } from 'vue'

const name = ref('John Doe')
const status = ref(true)
const tasks = ref(['task 1', 'task 2', 'task 3'])

const toggleStatus = () => {
  status.value = !status.value
}
</script>
<template>
  <h1>Hello {{ name }}</h1>
  <p v-if="status">you are active</p>
  <p v-else>you are inactive</p>
  <a :href="link">Look for me</a>
  <br />
  <br />
  <ul>
    <li v-for="task in tasks" :key="task">{{ task }}</li>
  </ul>
  <br />
  <button @click="toggleStatus">LogIn/Out</button>
</template>
