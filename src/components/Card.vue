<script setup>
defineProps({
    title: String,
    content: String
})

const emit = defineEmits(['show'])
</script>

<template>
    <div class="container">
        <h3 class="title">
            {{ title }}
        </h3>
        <div class="content">
            {{ content }}
        </div>
        <div class="btn">
            <button @click="emit('show', true)">Cadastrar</button>
        </div>
    </div>
</template>

<style scoped>
.container {
    display: flex;
    flex-direction: column;

    width: 250px;
    height: 250px;

    padding: 20px;
    border: 1px solid;
    border-radius: 10%;
    box-shadow: 1px 2px #888888;
}

.title {
    font-family: Arial, Helvetica, sans-serif;
}

.content {
    font-family: Arial, Helvetica, sans-serif;
}

.btn {
    margin-top: 20px;
}
</style>

