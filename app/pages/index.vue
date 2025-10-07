<template>
  <div class="w-full min-h-screen flex flex-col items-center">
    <StudentHome v-if="role === 'student'" />
    <AdminHome v-else-if="role === 'admin'" />
    <public-home v-else-if="role === 'public'" />
  </div>
</template>

<script setup>
import AdminHome from "~/components/adminHome.vue";
import StudentHome from "~/components/studentHome.vue";

const role = ref("admin");
</script>

<style scoped></style>
