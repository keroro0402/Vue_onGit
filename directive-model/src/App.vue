<script setup lang="ts">
import { ref, computed } from 'vue'

const inputNameBind = ref('斉藤ななみ')
const inputNameOn = ref('ななし')

const onInputName = (event: Event): void => {
  // eventはtypeScriptではEventTarget型を明示しないとだめ
  const element = event.target as HTMLInputElement // EventTarget型からはvalueは取り出せないので一度、HTMLInputElement型に変換する
  inputNameOn.value = element.value
}

const inputTextarea = ref('テキストエリアへの入力')

const memberType = ref(1)
const memberTypeSelect = ref('埼玉')

const agreeInit = ref('同意しない')

const selectedOS = ref([])
</script>
<template>
  <section>
    <input v-model="selectedOS" type="checkbox" value="Windows" />Windows<br />
    <input v-model="selectedOS" type="checkbox" value="macOS" />macOS<br />
    <input v-model="selectedOS" type="checkbox" value="Linux" />Linux<br />
    <input v-model="selectedOS" type="checkbox" value="Android" />Android<br />
    <input v-model="selectedOS" type="checkbox" value="iOS" />iOS<br />

    <p>選択されたOS：{{ selectedOS }}</p>
  </section>
  <br />
  <section>
    <input type="checkbox" v-model="agreeInit" true-value="同意する" false-value="同意しない" />
    <p>同意結果：{{ agreeInit }}</p>
  </section>

  <input type="text" v-bind:value="inputNameBind" />
  <br /><br />
  <input type="text" v-on:input="onInputName" />
  <p>{{ inputNameOn }}</p>

  <textarea v-model="inputTextarea"></textarea>
  <section>
    <input type="radio" v-model="memberType" value="1" />通常会員<br />
    <input type="radio" v-model="memberType" value="2" />特別会員<br />
    <input type="radio" v-model="memberType" value="3" />優良会員<br />

    <p>選択されたラジオボタン：{{ memberType }}</p>
  </section>
  <br />
  <section>
    <select v-model="memberTypeSelect">
      <option value="埼玉">埼玉</option>
      <option value="広島">広島</option>
      <option value="鳥取">鳥取</option>
      <option value="大阪">大阪</option>
      <option value="東京">東京</option>
      <option value="香川">香川</option>
    </select>
    <p>選択されたセレクトボックス：{{ memberTypeSelect }}</p>
  </section>
</template>
