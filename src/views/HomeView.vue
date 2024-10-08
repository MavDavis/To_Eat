<script setup lang="ts">
import { ref } from 'vue'
const restaurantList = ref<string[]>([])
const newRestaurantName = ref<string>('')
const submitRestaurantName = () => {
  restaurantList.value.push(newRestaurantName.value)
}
</script>

<template>
  <main>
    <h1>Home page</h1>
    <form @submit.prevent="submitRestaurantName">
      <input type="text" v-model="newRestaurantName" />
      <button>submit</button>
    </form>
    <ul>
      <li v-for="item in restaurantList" :key="item">{{ item }}</li>
    </ul>
  </main>
</template>
