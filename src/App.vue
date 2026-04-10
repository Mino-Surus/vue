<script setup>
import { ref } from 'vue';

const arrs = ref([
  {id: 1, tt:'hello' },
  {id: 2, tt:'bye' },
  {id: 3, tt:'play' }
])


let deleteElement = (arr) => {
  arrs.value = arrs.value.filter(a => a != arr)
}

let addItem = (arr) =>

</script>

<template>
  <p> ПРивет медвед</p>
  <ul>
    <li v-for="arr in arrs" :key="id">
        {{ arr.tt }}
        <button v-on:submit.prevent="deleteElement(arr)"></button>
    </li>
  </ul>
  <form>
    <input v-model="arrs">
    <button @click="addItem"> Добавить </button>
  </form>
</template>

<style scoped></style>

