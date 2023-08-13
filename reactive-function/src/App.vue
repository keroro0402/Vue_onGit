<script setup lang="ts">
import { reactive } from 'vue'

const personInit = {
  name: '斉藤ななみ',
  age: 32,
  sayHello: function () {
    console.log(`${this.name}です`)
  }
}
const person = reactive(personInit) // オブジェクトをリアクティブにする時はreactive()メソッドで一気にリアクティブにできるので使うべし！！

person.sayHello()
</script>
<template>
  <p>私の名前は {{ person['name'] }} です。</p>
  <p>年齢は {{ person.age }} 歳です。</p>
</template>
