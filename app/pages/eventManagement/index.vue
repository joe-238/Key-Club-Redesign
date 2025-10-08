<template>
  <div class="w-full">
    <subPageMenu :pages="eventManagementLinks" :active="'Events'" class="" />
  </div>
</template>

<script setup>
import subPageMenu from "~/components/subPageMenu.vue";
const eventManagementLinks = [
  {
    name: "Events",
    path: "/eventManagement",
  },
  {
    name: "Funds",
    path: "/eventManagement/funds",
  },
  {
    name: "Funds",
    path: "/eventManagement/funds",
  },
];
</script>

<style lang="scss" scoped></style>
