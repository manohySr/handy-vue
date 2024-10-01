<script setup>
import { ref } from 'vue'

const name = ref('John Doe')
const status = ref(true)
const tasks = ref(['task 1', 'task 2', 'task 3'])
const newTask = ref('')

const toggleStatus = () => {
  status.value = !status.value
}

const addTask = () => {
  if (newTask.value != '') {
    tasks.value.push(newTask.value)
    newTask.value = ''
  }
}

const deleteTask = (index) => {
  tasks.value.splice(index, 1)
}
</script>
<template>
  <h1>Hello {{ name }}</h1>
  <p v-if="status">you are active</p>
  <p v-else>you are inactive</p>
  <a :href="link">Look for me</a>

  <br />
  <br />

  <form @submit.prevent="addTask">
    <input v-model="newTask" />
    <button type="submit">Submit</button>
  </form>

  <br />
  <br />
  <ul>
    <li v-for="(task, index) in tasks" :key="task">
      <span>
        {{ task }}
      </span>
      <span>&nbsp;&nbsp;&nbsp;</span>
      <button @click="deleteTask(index)">X</button>
    </li>
  </ul>
  <br />
  <button @click="toggleStatus">LogIn/Out</button>
</template>
