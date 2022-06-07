<template lang="pug">
button( @click= "link--" ) -1
button( @click= "[link++, log(link)]" ) +1
hr
img(:src="image")

</template>

<script setup>
import { ref, computed } from 'vue'
const link = ref('2')
const image = computed(() => {
  return new URL('../assets/img/' + link.value + '.png', import.meta.url).href
})
// const image = ref(new URL('../assets/img/' + link.value + '.png', import.meta.url).href)
const log = function (n) {
  console.log(n)
}
</script>
