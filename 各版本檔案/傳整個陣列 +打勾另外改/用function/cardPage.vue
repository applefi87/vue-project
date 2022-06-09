<template lang="pug">
.card
  img(:src="'https://picsum.photos/300/200/?random=' + i.picnum")
  h3 {{ i.text }}
  hr
  button(v-if="i.good" @click="change") 收回讚
  button(v-else @click="change") 讚
</template>

<script setup>
const props = defineProps({
  i: Object,
  g: Boolean
})

// ***用物件改:
// 版本一(有emit比較正常)
// 正規改法?:
const emit = defineEmits(['update:i'])

const change = () => {
  const item = props.i
  item.good = !item.good
  emit('update:i', item)
}

// // 版本二(雖vscode報錯但物件內仍可改)
// const change = () => {
//   props.i.good = !props.i.good
// }

// ***用物件內值改:
// 版本一(有emit比較正常)
// const emit = defineEmits(['update:g'])
// const change = () => {
//   emit('update:g', !props.g)
// }

// // 版本二(單變數就不能硬改)
// const change = () => {
//   props.g = !props.g
// }

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
