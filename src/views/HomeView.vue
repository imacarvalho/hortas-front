<script setup>
import { ref } from 'vue'

const number1 = ref()
const number2 = ref()
const media = ref()

function calcularMedia() {
  media.value = (number1.value + number2.value) / 2

}

</script>

<template>
  <div>
    <!-- two way data bind -->
    <input type="number" placeholder="número 1" v-model="number1">
    <input type="number" placeholder="número 2" v-model="number2">
    <button @click="calcularMedia">Média</button>
    <p>{{ media }}</p>
    
  </div>
</template>

<style></style>