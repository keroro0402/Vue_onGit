<script setup lang="ts">
import { ref } from 'vue'

const result = ref('まだです')
let htmlStr = ref()
let count = ref(1)
const onclick = (): void => {
  if (count.value > 4) {
    count.value = 0
  }
  count.value++
  htmlStr.value = "<img src='./src/assets/item" + count.value + ".jpg'>"
  result.value = ''
}
const onchange = (): void => {
  console.log('sa')
}
</script>
<template>
  <section>
    <p>
      <input v-on:click="onclick" type="button" value="クリック1" />
      <input v-on:change="onchange" value="10" type="number" />
    </p>
    <p><span v-html="htmlStr"></span>{{ result }}</p>
  </section>
</template>
