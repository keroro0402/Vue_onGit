<script setup lang="ts">
import { ref, computed } from 'vue'

const PIInit = Math.PI
const PI = ref(Math.floor(PIInit * 100) / 100)

const radiusInit = Math.ceil(Math.random() * 10) + 3
let radius = ref(radiusInit)

setInterval(() => {
  radius.value = Math.ceil(Math.random() * 10) + 3
}, 2000)

const area = computed((): string => {
  return radius.value * radius.value * PI.value
})
</script>
<template>
  <p>円周率：{{ PI }}</p>
  <p>半径：{{ radius }}</p>
  <p>の円の面積は</p>
  <p>{{ area }}</p>
  <p>です</p>
</template>
