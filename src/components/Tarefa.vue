<script setup>
defineProps({
    descricaoTarefa: String
})

const emit = defineEmits(["editar", "excluir"])
</script>

<template>
    <div class="container">
    <br>    
    <span>{{ descricaoTarefa }}</span>
    <br>
    <button @click="emit('editar')">Editar</button>
    <br>
    <button @click="emit('excluir')">Excluir</button>
    <br>
</div>
</template>

<style scoped>
.container{
display: flex;
margin: 8px;
flex-direction: column;
align-items: center;

width:30%;
height: 30%;

padding:20;
border: 1 px solid;
border-radius: 10%;
box-shadow: 1px 1px 1px 1px #000000;
}
.title{
    font-family: Arial, Helvetica, sans-serif;
}
</style>