<script setup lang="ts">
import { ref } from 'vue'
//import { ref } from 'vue'
//import {ref} from "vue"

const name1 = ref('斉藤ななみ') // ref関数：テンプレート変数
const name2 = ref('佐々木希')
</script>
<template>
  <!--マスタッシュ構文-->
  <p>{{ name1 }}</p>
  <p>{{ name2 }}</p>
  <p>こんにちは</p>
</template>
