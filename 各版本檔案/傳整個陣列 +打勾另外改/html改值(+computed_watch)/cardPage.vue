<template lang="pug">
.card
  img(:src="'https://picsum.photos/300/200/?random=' + i.picnum")
  h3 {{ i.text }}
  hr
  button(v-if="i.good" @click="i.good = false") 收回讚
  button(v-else @click="i.good = true") 讚
  //- 取消computed 記得刪除下行
  | {{x}}
</template>

<script setup>
//  感覺用function帶動emit跨檔改比較合法
// 請見function改值，會發現其實vscode有報錯，只是用html改沒被偵測到

import { computed, watch } from 'vue'

// 整個script可以只有下行就好(上面也可刪)，html可改值沒測到錯誤
const props = defineProps({
  i: Object
})

// // 下方整個emit方法竟然不用 也許跟物件淺層複製有關?
// const emit = defineEmits(['update:i'])

// // ***computed 操作法(失敗，這裡沒更新成功，上面就直接更新了)
// const x = computed(() => {
//   emit('update:i', '111')
//   return props.i.good
// })

// ***watch 操作法 (有問題，不知是這裡更新成功/上面就直接更新了)
// watch(props.i, () => {
//   emit('update:i', props.i)
//   console.log(props.i.good)
// })

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
