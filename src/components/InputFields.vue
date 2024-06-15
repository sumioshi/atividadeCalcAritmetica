<template>
    <div class="mb-3">
      <label for="num1" class="form-label">Número 1</label>
      <input :value="num1" @input="updateNum1" type="number" class="form-control" id="num1">
      
      <label for="num2" class="form-label">Número 2</label>
      <input :value="num2" @input="updateNum2" type="number" class="form-control" id="num2">
    </div>
  </template>
  
  <script setup>
  const props = defineProps({
    num1: Number,
    num2: Number
  });
  
  const emit = defineEmits(['update:num1', 'update:num2']);
  
  const updateNum1 = (event) => {
    emit('update:num1', parseFloat(event.target.value));
  };
  
  const updateNum2 = (event) => {
    emit('update:num2', parseFloat(event.target.value));
  };
  </script>
  