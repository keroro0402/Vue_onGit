<script setup lang="ts">
import { ref, computed, reactive } from 'vue'

const result = ref()
const onclick = (): void => {
  result.value = 'ネットワークとネットワークを繋げる機器'
}
let flg = true
const answer = ref('未回答')
const onclick2 = (data): void => {
  console.log(data)
  if (data) {
    answer.value = '他のネットワークへの出入り口のこと。家庭用ルータは基本ハブ・ルータ'
    flg = !flg
  } else {
    answer.value = '未回答'
    flg = !flg
  }
}

const ob1 = {
  name: '斉藤'
}

const ob2 = {
  name2: 'ななみ'
}

Object.assign(ob1, ob2)
console.log(ob1)

const array = [1, 2, 3, 4, 5]
const [a, b, c, ...other] = array
console.log(a)
console.log(other)
console.log(b)
</script>
<template>
  <p><input v-on:click="onclick" type="button" value="押す" /></p>
  <p>ハブとルータの違いは・・・</p>
  <p>ハブ：複数のPCをネットワークを繋ぐ機器</p>
  <p>ルータ：{{ result }}</p>
  <br />
  <p>デフォルトゲートウェイを説明せよ</p>
  <p><input type="button" value="押す" v-on:click="onclick2(flg)" /></p>
  <p>{{ answer }}</p>
</template>
