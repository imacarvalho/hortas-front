<script setup>
import { computed, ref, watch } from 'vue'

const number1 = ref(0)
const number2 = ref(0)

const media = computed(() => (number1.value + number2.value) / 2)

watch(() => number1.value, (newValue, oldValue) => {
  console.log('newValue', newValue)
  console.log('oldValue', oldValue)
})

</script>

<template>
  <div>
    <!-- two way data bind -->
    <input type="number" placeholder="número 1" v-model="number1">
    <input type="number" placeholder="número 2" v-model="number2">
    <!-- <button @click="calcularMedia">Média</button> -->

    <p v-show="media">{{ media }}</p>
  </div>
</template>

<style></style>