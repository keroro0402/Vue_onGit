<script setup lang="ts">
import { ref, reactive } from 'vue'

const personInit = {
  name: '斉藤ななみ',
  age: 32,
  sayHello: function () {
    console.log(`${this.name}です`)
  }
}
const person = reactive(personInit) // オブジェクトをリアクティブにする時はreactive()メソッドで一気にリアクティブにできるので使うべし！！

person.sayHello()

const img = ref('/src/assets/item1.jpg')
</script>
<template>
  <img v-bind:src="img" />
  <p>※※※※※※※※※※※※※※</p>
  <p>私の名前は {{ person['name'] }} です。</p>
  <p><img src="./assets/img/item2.jpg" /></p>
  <p>年齢は {{ person.age }} 歳です。</p>
  <p><img src="./assets/item1.jpg" /></p>
</template>
