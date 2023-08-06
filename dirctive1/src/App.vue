<script setup lang="ts">
import { ref, computed, reactive } from 'vue'

interface Member {
  name: string
  age: number
  sex: string
}

const people = {
  name: '斉藤ななみ',
  age: 32,
  sex: '女'
}

const nanami: Member = reactive(people)
</script>
<template>
  <p>{{ nanami.name }}／{{ nanami.age }}／{{ nanami.sex }}</p>
  <p><img src="@/assets/6.jpeg" /></p>
  <br />
  <p><img src="@/assets/Piyoko.png" /></p>
</template>
