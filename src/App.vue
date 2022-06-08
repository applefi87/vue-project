<script setup>
import cardPage from './components/cardPage.vue'
import { ref } from 'vue'

const num = ref(0)
const numFn = i => {
  num.value = i
}
</script>

<template lang="pug">
| 按讚總數={{ num }}
br
cardPage(v-model:numb="num")

</template>
