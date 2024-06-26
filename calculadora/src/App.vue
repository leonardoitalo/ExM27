<script setup lang="ts">
import { ref, computed } from 'vue'

const num1 = ref(0)
const num2 = ref(0)
const selectedOperation = ref('soma')

const result = computed(() => {
  switch (selectedOperation.value) {
    case 'soma':
      return num1.value + num2.value
    case 'sub':
      return num1.value - num2.value
    case 'multi':
      return num1.value * num2.value
    case 'divi':
      return num2.value !== 0 ? num1.value / num2.value : 'Divisão por zero!'
    default:
      return 0
  }
})
</script>

<template>
  <div class="container d-flex flex-column">
    <input type="number" v-model.number="num1" placeholder="Número 1">
    <input type="number" v-model.number="num2" placeholder="Número 2">
    <select v-model="selectedOperation">
      <option value="soma">Soma</option>
      <option value="sub">Subtração</option>
      <option value="multi">Multiplicação</option>
      <option value="divi">Divisão</option>
    </select>
    <span>{{ result }}</span>
  </div>
</template>

<style scoped></style>
