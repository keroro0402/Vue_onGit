<script setup lang="ts">
import { ref, computed } from 'vue'
const randomInit = Math.random()
const radiusInit = Math.floor(randomInit * 10)
let radius = ref(radiusInit)
let PI = Math.floor(Math.PI * 100) / 100
const f = () => {
  radius.value = Math.floor(Math.random() * 10 + 4)
}
setInterval(f, 1000)

const area = computed((): number => {
  return radius.value * radius.value * PI
})
</script>
<template>
  <p>半径：{{ radius }}、円周率：{{ PI }}</p>
  <p>の円の面積は{{ area }}です</p>
</template>
