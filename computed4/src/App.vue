<script setup lang="ts">
import { ref, computed } from 'vue'
let radiusInit = Math.round(Math.random() * 10)
const PI = Math.floor(Math.PI * 100) / 100

const radius = ref(radiusInit)
const area = computed((): number => {
  // Vueで何かを計算する時は必ずcomputed関数を使う
  // スクリプトブロック内で参照する時は『変数名.value』を使う
  // 算出プロパティは『読み取り専用』なのでそのまま代入はできない
  return radius.value * radius.value * PI
})

//area.value = 'sasa'
let y = area.value
y = 5000

setInterval(() => {
  radius.value = Math.floor(Math.random() * 10 + 10)
}, 1000)
</script>
<template>
  <p>半径{{ radius }}の円の面積は{{ area }}です</p>
</template>
