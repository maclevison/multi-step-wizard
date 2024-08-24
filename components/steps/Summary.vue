<script setup>
defineProps(['formData']);
</script>

<template>
  <div class="space-y-4">
    <h2 class="text-2xl font-bold">Summary</h2>
    <div class="space-y-2">
      <p><strong>Name:</strong> {{ formData.name }}</p>
      <p><strong>Email:</strong> {{ formData.email }}</p>
      <p><strong>Company Size:</strong> {{ formData.companySize }}</p>
      <p><strong>Role:</strong> {{ formData.role }}</p>
      <p><strong>Goals:</strong> {{ formData.goals }}</p>
      <p><strong>Preferred Contact:</strong> {{ formData.preferredContact }}</p>
    </div>
  </div>
</template>