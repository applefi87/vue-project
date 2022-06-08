<script setup>
import { reactive, watch } from 'vue'
const arr = reactive([
  { picnum: 1, text: '111', good: false },
  { picnum: 2, text: '222', good: false },
  { picnum: 3, text: '333', good: false },
  { picnum: 4, text: '444', good: false },
  { picnum: 5, text: '555', good: false }
])

const emit = defineEmits(['numb'])

watch(arr, (n, o) => {
  const nums = arr.filter(i => { return i.good }).length
  console.log(nums)
  emit('update:numb', nums)
})

</script>

<template lang="pug">
.card(v-for="i in arr")
  img(:src="'https://picsum.photos/300/200/?random=' + i.picnum")
  h3 {{ i.text }}
  hr
  button(v-if="i.good" @click="i.good = false") 收回讚
  button(v-else @click="i.good = true") 讚
</template>

<style scoped lang="sass">
.card
  width: 100px
  display: inline-block
  margin: 10px
  border-radius: 5px
  border: 1px solid black
  box-shadow: 3px 3px 3px black
  img
    width: 100%
</style>
