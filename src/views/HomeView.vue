<script setup>
import Usuarios from '@/components/Usuarios.vue';
import { ref } from 'vue';

const user = ref()
const listaUsuarios = ref([])
const editando = ref(false)
const indexEdit = ref()

function cadastrar() {
  if (!user.value) {
    return alert("Input inválido")
  }
  if (editando.value) {
    listaUsuarios.value.splice(indexEdit, 1, user.value)
  } else {
    listaUsuarios.value.push(user.value)
  }
  editando.value = false

  user.value = ""
}

function editar(item, index) {
  user.value = item
  editando.value = true
  indexEdit.value = index
}

function excluir(index) {
  listaUsuarios.value.splice(index, 1)
}

</script>

<template>
  <div class="container">
    <!-- <Card title="Usuário" :content="content" @show="showCard = $event" /> -->
    <label>Cadastro de Usuário</label>
    <div>
      <input type="text" v-model="usuário">
      <button @click="cadastrar">Novo Usuário</button>
    </div>
    <div v-for="(item, index) in listaUsuarios" :key="item">
      <User :descricao-Usuario="item" @editar="editar(item, index)" @excluir="excluir(index)" />
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