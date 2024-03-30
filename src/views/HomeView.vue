<script setup>
import Card from '@/components/Card.vue';
import { ref } from 'vue';

const showCard = ref(false)

</script>

<template>
  <div class="container">
    <Card title="Lorem ipsum dolor sit" :content="content" @show="showCard = $event" />
    <Dialog :show="showCard"/>
  </div>
</template>

<style scoped>
.container {
  display: flex;
}
</style>