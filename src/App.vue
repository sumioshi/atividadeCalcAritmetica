<template>
  <div class="container mt-5">
    <h1 class="mb-4">Calculadora Aritmética</h1>
    <InputFields :num1="num1" :num2="num2" @update:num1="num1 = $event" @update:num2="num2 = $event" />
    <SelectOperation :operation="operation" @update:operation="operation = $event" />
    <ResultDisplay :result="result" />
  </div>
</template>

<script setup>
import { reactive, computed } from 'vue';
import InputFields from './components/InputFields.vue';
import SelectOperation from './components/SelectOperation.vue';
import ResultDisplay from './components/ResultDisplay.vue';

const state = reactive({
  num1: 0,
  num2: 0,
  operation: '+'
});

const result = computed(() => {
  switch (state.operation) {
    case '+':
      return state.num1 + state.num2;
    case '-':
      return state.num1 - state.num2;
    case '*':
      return state.num1 * state.num2;
    case '/':
      return state.num2 !== 0 ? state.num1 / state.num2 : 'Erro: Divisão por zero';
    default:
      return 0;
  }
});

const num1 = computed({
  get: () => state.num1,
  set: (value) => state.num1 = value
});

const num2 = computed({
  get: () => state.num2,
  set: (value) => state.num2 = value
});

const operation = computed({
  get: () => state.operation,
  set: (value) => state.operation = value
});
</script>

<style>
body {
  background-color: #f8f9fa;
}
</style>
