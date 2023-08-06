<script setup lang="ts">
import { ref, computed, reactive } from 'vue'

const peopleInit = {
  firstName: '斉藤',
  lastName: 'ななみ'
}

const imgStyle = {
  width: '30%'
}

const imgEl = {
  src: './src/assets/item3.jpg'
}

const people = reactive(peopleInit)

let count = ref(0)

const onclick = (): void => {
  setInterval(() => {
    count.value++
  }, 1000)
}
</script>
<template>
  <p><input v-on:click="onclick" type="button" value="押す" /></p>
  <p>{{ count }}</p>
  <br />
  <p>{{ people.firstName }}</p>
  <p>バインディングで表示した画像</p>
  <p><img v-bind:src="imgEl.src" /></p>
  <p>assets/に画像を入れた場合</p>
  <p><img v-bind:style="imgStyle" src="./assets/item1.jpg" /></p>
  <br />
  <p>assets/img/に画像を入れた場合</p>
  <p><img v-bind:style="imgStyle" src="./assets/img/item3.jpg" /></p>
</template>
