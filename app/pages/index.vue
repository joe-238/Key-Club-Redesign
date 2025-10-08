<template>
  <div class="w-full h-screen flex flex-col items-center overflow-scroll">
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
