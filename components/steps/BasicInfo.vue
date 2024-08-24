<script setup>
defineProps(['formData']);
const emit = defineEmits(['update']);

const updateField = (field, value) => {
  emit('update', field, value);
};
</script>

<template>
  <div class="space-y-4">
    <h2 class="text-2xl font-bold">Basic Information</h2>
    <div class="space-y-2">
      <label for="name" class="block text-sm font-medium text-gray-700">Full Name</label>
      <input 
        id="name" 
        v-model="formData.name" 
        @input="updateField('name', $event.target.value)"
        class="mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:border-blue-300 focus:ring focus:ring-blue-200 focus:ring-opacity-50"
        placeholder="John Doe"
      />
    </div>
    <div class="space-y-2">
      <label for="email" class="block text-sm font-medium text-gray-700">Email Address</label>
      <input 
        id="email" 
        type="email" 
        v-model="formData.email" 
        @input="updateField('email', $event.target.value)"
        class="mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:border-blue-300 focus:ring focus:ring-blue-200 focus:ring-opacity-50"
        placeholder="john@example.com"
      />
    </div>
  </div>
</template>