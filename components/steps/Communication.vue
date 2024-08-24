<script setup>
defineProps(['formData']);
const emit = defineEmits(['update']);

const updateField = (field, value) => {
  emit('update', field, value);
};
</script>

<template>
  <div class="space-y-4">
    <h2 class="text-2xl font-bold">Communication Preferences</h2>
    <div class="space-y-2">
      <label class="block text-sm font-medium text-gray-700">Preferred method of contact</label>
      <div class="mt-2 space-y-2">
        <div class="flex items-center">
          <input 
            id="email" 
            type="radio" 
            value="email" 
            v-model="formData.preferredContact" 
            @change="updateField('preferredContact', $event.target.value)"
            class="focus:ring-blue-500 h-4 w-4 text-blue-600 border-gray-300"
          />
          <label for="email" class="ml-3 block text-sm font-medium text-gray-700">Email</label>
        </div>
        <div class="flex items-center">
          <input 
            id="phone" 
            type="radio" 
            value="phone" 
            v-model="formData.preferredContact" 
            @change="updateField('preferredContact', $event.target.value)"
            class="focus:ring-blue-500 h-4 w-4 text-blue-600 border-gray-300"
          />
          <label for="phone" class="ml-3 block text-sm font-medium text-gray-700">Phone</label>
        </div>
        <div class="flex items-center">
          <input 
            id="inApp" 
            type="radio" 
            value="inApp" 
            v-model="formData.preferredContact" 
            @change="updateField('preferredContact', $event.target.value)"
            class="focus:ring-blue-500 h-4 w-4 text-blue-600 border-gray-300"
          />
          <label for="inApp" class="ml-3 block text-sm font-medium text-gray-700">In-app messaging</label>
        </div>
      </div>
    </div>
  </div>
</template>