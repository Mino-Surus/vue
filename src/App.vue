<script setup>
import { ref } from 'vue';

const arrs = ref([
  {id: 1, tt:'hello' },
  {id: 2, tt:'bye' },
  {id: 3, tt:'play' }
])
</script>

<template>
  <ul>
    <li v-for="arr in arrs">
        {{ arrs.tt }}
    </li>
  </ul>
</template>

<style scoped></style>

