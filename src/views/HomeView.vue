<script setup>
import { ref } from 'vue'

const name = ref('')
const age = ref()
const user = ref()

function createUser() {
  user.value = {
    name: name.value,
    age: age.value
  }
}

</script>

<template>
  <div>
    <!-- two way data bind -->
    <input type="text" placeholder="Nome" v-model="name">
    <input type="number" placeholder="Idade" v-model="age">
    <button @click="createUser">Cadastrar</button>
    <p v-show="user?.name">Nome: {{ user?.name }}</p>
    <p v-if="user?.age">Idade: {{ user?.age }}</p>
    
  </div>
</template>

<style></style>