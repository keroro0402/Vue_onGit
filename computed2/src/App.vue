<script setup lang="ts">
import { ref, computed, reactive } from 'vue'

const PIInit = Math.PI
const PI = ref(Math.floor(PIInit * 100) / 100)

const radiusInit = Math.ceil(Math.random() * 10) + 3
let radius = ref(radiusInit)

setInterval(() => {
  radius.value = Math.ceil(Math.random() * 10) + 3
}, 2000)

const area = computed((): number => {
  return radius.value * radius.value * PI.value
})

interface User {
  firstName: string
  lastName: string
  age: number
  sex: string
  name?: string
}

const personInit = {
  firstName: '斉藤',
  lastName: 'ななみ',
  age: 32,
  sex: '女'
}

const person: User = reactive(personInit)

person.name = person.firstName + person.lastName
</script>
<template>
  <p>円周率：{{ PI }}</p>
  <p>半径：{{ radius }}</p>
  <p>の円の面積は</p>
  <p>{{ area }}</p>
  <p>です</p>
  <br />
  <p>{{ person.name }}</p>
  <p>{{ person.age }}</p>
  <p>{{ person.sex }}</p>
</template>
