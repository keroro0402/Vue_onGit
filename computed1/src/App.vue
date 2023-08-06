<script setup lang="ts">
import { ref, computed } from 'vue'
const title1 = ref('コンピュータの豆知識をメモ')

const q1 = ref('LAN')
const q2 = ref('WAN')

const q = computed((): string => {
  return q1.value + 'と' + q2.value + 'の違いは・・・'
})
const q3 = computed((): string => {
  return `${q1.value}は家内や社内など小規模のネットワーク`
})
const q4 = computed((): string => {
  return `${q2.value}は電気通信業者が設置した環境を使う大規模なネットワーク`
})

const q5 = computed((): string => {
  return `ネットワークは${q1.value}と${q2.value}の２種類に分類される`
})
</script>

<template>
  <h2>{{ title1 }}</h2>
  <br />
  <p>{{ q5 }}</p>
  <p>{{ q }}</p>
  <p>{{ q3 }}</p>
  <p>{{ q4 }}</p>
</template>
