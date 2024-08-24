<script setup>
defineProps(['formData']);
const emit = defineEmits(['update']);

const updateField = (field, value) => {
  emit('update', field, value);
};
</script>

<template>
  <div class="space-y-4">
    <h2 class="text-2xl font-bold">Company Information</h2>
    <div class="space-y-2">
      <label for="companySize" class="block text-sm font-medium text-gray-700">Company Size</label>
      <select 
        id="companySize" 
        v-model="formData.companySize" 
        @change="updateField('companySize', $event.target.value)"
        class="mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:border-blue-300 focus:ring focus:ring-blue-200 focus:ring-opacity-50"
      >
        <option value="">Select company size</option>
        <option value="1-10">1-10 employees</option>
        <option value="11-50">11-50 employees</option>
        <option value="51-200">51-200 employees</option>
        <option value="201+">201+ employees</option>
      </select>
    </div>
    <div class="space-y-2">
      <label for="role" class="block text-sm font-medium text-gray-700">Your Role</label>
      <input 
        id="role" 
        v-model="formData.role" 
        @input="updateField('role', $event.target.value)"
        class="mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:border-blue-300 focus:ring focus:ring-blue-200 focus:ring-opacity-50"
        placeholder="e.g. Marketing Manager"
      />
    </div>
  </div>
</template>