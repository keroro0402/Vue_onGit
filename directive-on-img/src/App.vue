<script setup lang="ts">
import { ref } from 'vue'

const widthInit = '100'
let width = ref(widthInit)

const onchange = (event: Event): void => {
  const el = event.target as HTMLInputElement
  width.value = el.value
}
</script>
<template>
  <p><input type="number" v-on:change="onchange" v-bind:value="width" /></p>
  <p><img v-bind:width="width" src="./assets/item1.jpg" /></p>
</template>
