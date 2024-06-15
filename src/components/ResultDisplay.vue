<template>
    <div class="alert alert-primary" role="alert">
      Resultado: {{ result }}
    </div>
  </template>
  
  <script setup>
  const props = defineProps({
    result: Number
  });
  </script>
  