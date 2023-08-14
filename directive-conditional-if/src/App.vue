<script setup lang="ts">
import { ref, computed } from 'vue'

const number = ref(80)
const img = ref('./src/assets/image.png')

const showOrNot = computed((): boolean => {
  let showOrNot = false
  const rand = Math.round(Math.random() * 100)
  if (rand >= 50) {
    showOrNot = true
  }
  return showOrNot
})

let flg = ref(true)
const showFlg = ref(flg)

const onclick = (): void => {
  flg.value = !flg.value
}
</script>
<template>
  <p v-if="number >= 50">条件に合致したので表示①</p>
  <p v-if="Math.round(Math.random() * 100) >= 50">条件に合致したので表示②</p>
  <p v-if="showOrNot">条件に合致したので表示③</p>
  <p><input type="button" value="表示・非表示" v-on:click="onclick" /></p>
  <p v-if="showFlg"><img v-bind:src="img" /></p>
</template>
