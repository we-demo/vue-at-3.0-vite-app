<script setup>
import { ref, reactive } from 'vue'
import VueAt from 'vue-at'

defineProps({
  msg: String
})

const count = ref(0)

let at = reactive({
  members: [
    'Bill Gates', 'Steve Jobs', '椿木', '小浩',
  ],
  text: 'xxx @椿木 @Bill Gates xxx...',
})
</script>

<template>
  <h1>{{ msg }}</h1>

  <VueAt :members="at.members" v-model:value="at.text">
    <div class="editor" contenteditable=""></div>
  </VueAt>

  <div class="card">
    <button type="button" @click="count++">count is {{ count }}</button>
    <p>
      Edit
      <code>components/HelloWorld.vue</code> to test HMR
    </p>
  </div>

  <p>
    Check out
    <a href="https://vuejs.org/guide/quick-start.html#local" target="_blank"
      >create-vue</a
    >, the official Vue + Vite starter
  </p>
  <p>
    Install
    <a href="https://github.com/johnsoncodehk/volar" target="_blank">Volar</a>
    in your IDE for a better DX
  </p>
  <p class="read-the-docs">Click on the Vite and Vue logos to learn more</p>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}

.editor {
  white-space: pre-wrap;
  overflow: hidden;
  resize: none;
  background-color: rgba(0, 255, 255, .02);
  border: solid 1px gray;
  padding: .4em 1em;
  max-width: 30em;
  height: 5em;
}
</style>
