<script setup>
import Card from '@/components/Card.vue';
import { ref } from 'vue';

const tarefa = ref()
const listaTarefas = ref([])
const editando = ref(false)
const indexEdit = ref()

function cadastrar() {
  if (!tarefa.value) {
    return alert("Input inválido")
  }
  if (editando.value) {
    listaTarefas.value.splice(indexEdit, 1, tarefa.value)
  } else {
    listaTarefas.value.push(tarefa.value)
  }
  editando.value = false

  tarefa.value = ""
}

function editar(item, index) {
  tarefa.value = item
  editando.value = true
  indexEdit.value = index
}

function excluir(index) {
  listaTarefas.value.splice(index, 1)
}

</script>

<template>
  <div class="container">
    <!-- <Card title="Tarefa" :content="content" @show="showCard = $event" /> -->
    <label>Tarefa</label>
    <div>
      <input type="text" v-model="tarefa">
      <button @click="cadastrar">Cadastrar</button>
    </div>
    <div v-for="(item, index) in listaTarefas" :key="item">
      {{ item }}
      <button @click="editar(item, index)">Editar</button>
      <button @click="excluir(index)">Excluir</button>

    </div>

  </div>
</template>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  width: 40%
}
</style>