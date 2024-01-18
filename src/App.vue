<script setup lang="ts">
import { ref } from 'vue'

const count = ref(0)
const text = ref('')

function increment() {
  count.value++
}

function decrement() {
  count.value--
}

const reset = () => {
  count.value = 0
}

const clearText = () => {
  text.value = ''
}
</script>

<template>
  <h1 class="bg-black">Testando Vue</h1>
  <div class="containerTests">
    <div class="test1">
      <h2>Reatividade with Numbers</h2>
      <div v-if="count >= 0">Valor atual: {{ count }}</div>
      <div v-if="count < 0">Valor abaixo de zero!!</div>
      <div class="buttonGroup">
        <button @click="increment">Add +1</button>
        <button @click="decrement">Remove -1</button>
        <button @click="reset">Reset to zero</button>
      </div>
    </div>
    <div class="test2">
      <h2>Reatividade with Strings</h2>
      <p>You writted: {{ text }}</p>
      <input type="text" v-model="text" placeholder="Write something" />
      <div class="buttonGroup">
        <button @click="clearText">Clear</button>
      </div>
    </div>
  </div>
</template>

<style scoped>
.buttonGroup {
  display: flex;
  gap: 1rem;
  margin-top: 0.5rem;
}

.containerTests {
  display: flex;
  gap: 3rem;
  flex-wrap: wrap;
}

.test1 {
  border: 1px solid blue;
  padding: 1rem;
}
.test2 {
  border: 1px solid red;
  padding: 1rem;
}
</style>
