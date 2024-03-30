<script setup>
defineProps({
    descricaoTarefa: String
})

const emit = defineEmits(["editar", "excluir"])
</script>

<template>
    <span>{{ descricaoTarefa }}</span>
    <button @click="emit('editar')">Editar</button>
    <button @click="emit('excluir')">Excluir</button>
</template>