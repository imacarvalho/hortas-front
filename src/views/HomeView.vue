<script setup>
import { ref } from 'vue'

const persons = ref([
  {
    name: "Matheus",
    age: 29
  },
  {
    name: "Lucas",
    age: 30
  },
  {
    name: "Ivo",
    age: 18
  },
  {
    name: "Liliana",
    age: 20
  },
  {
    name: "Aline",
    age: 40
  },
])

</script>

<template>
  <div>
    <table>
      <tr>
        <th>Nome</th>
        <th>Idade</th>
      </tr>
      <tr v-for="(person, index) in persons" :key="index">
        <td>{{ person.name }}</td>
        <td>{{ person.age }}</td>
      </tr>
    </table>
  </div>
</template>

<style></style>