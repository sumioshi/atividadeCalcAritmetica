<template>
  <div class="mb-3">
    <label for="operation" class="form-label">Operação</label>
    <select :value="operation" @change="updateOperation" class="form-select" id="operation">
      <option value="+">+</option>
      <option value="-">-</option>
      <option value="*">*</option>
      <option value="/">/</option>
    </select>
  </div>
</template>

<script setup>
const props = defineProps({
  operation: String
});

const emit = defineEmits(['update:operation']);

const updateOperation = (event) => {
  emit('update:operation', event.target.value);
};
</script>
