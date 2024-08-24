<script setup>
defineProps(['formData']);
const emit = defineEmits(['update']);

const updateField = (field, value) => {
  emit('update', field, value);
};
</script>

<template>
  <div class="space-y-4">
    <h2 class="text-2xl font-bold">Goals and Objectives</h2>
    <div class="space-y-2">
      <label for="goals" class="block text-sm font-medium text-gray-700">What are your main goals for using our product?</label>
      <textarea 
        id="goals" 
        v-model="formData.goals" 
        @input="updateField('goals', $event.target.value)"
        class="mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:border-blue-300 focus:ring focus:ring-blue-200 focus:ring-opacity-50"
        placeholder="e.g. Improve team collaboration, increase productivity..."
        rows="4"
      ></textarea>
    </div>
  </div>
</template>