
<script setup>
import mainPage from './components/mainPage.vue'
import cardPage from './components/cardPage.vue'
import num from './components/cardPage.vue'

</script>

<template lang="pug">
//- mainPage
hr
| 按讚總數={{num}}
br
cardPage()
</template>

<style>
</style>
