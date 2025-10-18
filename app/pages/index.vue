<template>
  <div class="w-full h-screen flex flex-col items-center overflow-scroll">
    <StudentHome v-if="role === 'student'" />
    <AdminHome v-else-if="role === 'admin'" />
    <PublicHome v-else-if="role === 'public'" />
  </div>
</template>

<script setup>
const role = ref("admin");
</script>

<style scoped></style>
