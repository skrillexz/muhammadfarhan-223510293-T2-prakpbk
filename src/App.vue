<template>
  <div>
    <h1 :class="{ 'highlight': isHighlighted }">Contoh Halaman Web</h1>
    <p :style="{ fontSize: fontSize + 'px' }">contoh halaman web</p>
    <input type="text" v-model="inputText" placeholder="Ketik sesuatu..." @input="updateText">
    <p>Input teks: {{ inputText }}</p>
    <button @click="toggleHighlight">Toggle Highlight</button>
    <button @click="increaseFontSize">Increase Font Size</button>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const isHighlighted = ref(false);
const fontSize = ref(16);
const inputText = ref('');

const updateText = (event) => {
  inputText.value = event.target.value;
};

const toggleHighlight = () => {
  isHighlighted.value = !isHighlighted.value;
};

const increaseFontSize = () => {
  fontSize.value += 2;
};
</script>

<style scoped>
.highlight {
  color: blue;
}
</style>
