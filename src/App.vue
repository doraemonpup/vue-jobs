<script setup>
import { ref } from 'vue'

const name = ref('John Doe')
const status = ref('active')
const tasks = ref(['Task One', 'Task Two', 'Task Three'])

const toggleStatus = () => {
  if (status.value === 'active') {
    status.value = 'pending'
  } else if (status.value === 'pending') {
    status.value = 'inactive'
  } else {
    status.value = 'active'
  }
}
</script>

<template>
  <h1>{{ name }}</h1>

  <!-- v-if-else -->
  <p v-if="status === 'active'">User is active</p>
  <p v-else-if="status === 'pending'">User is pending</p>
  <p v-else>User is inactive</p>

  <!-- v-for -->
  <h3>Tasks:</h3>
  <ul>
    <li v-for="task in tasks" :key="task">{{ task }}</li>
  </ul>

  <!-- v-bind -->
  <!-- <a v-bind:href="link" target="_blank">Click for Googlge</a> -->
  <a :href="link" target="_blank">Click for Googlge</a>
  <br />

  <!-- v-on -->
  <!-- <button v-on:click="toggleStatus">Change Status</button> -->
  <button @click="toggleStatus">Change Status</button>
</template>
