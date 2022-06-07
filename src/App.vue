<script setup>
import mainPage from './components/mainPage.vue'
import cardPage from './components/cardPage.vue'
// import num from './components/cardPage.vue'
//
import { reactive, computed } from 'vue'
const arr = reactive([
  { picnum: 1, text: '111', good: false },
  { picnum: 2, text: '222', good: false },
  { picnum: 3, text: '333', good: false },
  { picnum: 4, text: '444', good: false },
  { picnum: 5, text: '555', good: false }
])
//
const num = computed(() => {
  return arr.filter(i => { return i.good }).length
})
</script>

<template lang="pug">
//- mainPage
hr
| 按讚總數={{ num }}
br
cardPage(v-for="i in arr" :i="i")
</template>

<style>
</style>
