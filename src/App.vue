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

let addItem = (arr) => {

}


// import Child from "./Child.vue"
// import {ref} from "vue"

// const mail = ref("mm@mail.ru")
</script>

<template>
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


<!-- <Child :num="mail" /> -->

</template>

<style scoped></style>

