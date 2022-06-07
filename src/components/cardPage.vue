<template lang="pug">
.card
  img(:src="'https://picsum.photos/300/200/?random=' + i.picnum")
  h3 {{ i.text }}
  hr
  button(v-if="i.good" @click="i.good = false") 收回讚
  button(v-else @click="i.good = true") 讚

</template>

<script setup>
import { reactive, ref } from 'vue'
const props = defineProps({
  i: Object
})
</script>

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
