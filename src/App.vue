<script setup>
import { ref } from 'vue';

const arrs = ref([
  {id: 1, tt:'hello', done: false },
  {id: 2, tt:'bye', done: false },
  {id: 3, tt:'play', done: false }
])


let deleteElement = (arr) => {
  arrs.value = arrs.value.filter(a => a.id != arr.id)
}

const newItem = ref('') 

let addItem = () => {
  if (newItem.value !=='') {
  arrs.value.push({id: arrs.value.length + 1, tt: newItem.value, done: false})
  newItem.value = ''
  }
}


// import Child from "./Child.vue"
// import {ref} from "vue"

// const mail = ref("mm@mail.ru")
</script>

<template>
  <ul>
    <li v-for="arr in arrs" :key="arr.id">
      <input type="checkbox" v-model="arr.done">
      <b :class="{ done: arr.done}">{{ arr.tt }}</b>
        <button v-on:click="deleteElement(arr)"> удалить </button>
    </li>
  </ul>
  <form v-on:submit.prevent>
    <input v-model="newItem">
    <button v-on:click="addItem"> Добавить </button>
  </form>


<!-- <Child :num="mail" /> -->

</template>

<style scoped>
.done {
  text-decoration: line-through;
  color: gray;
}
</style>

