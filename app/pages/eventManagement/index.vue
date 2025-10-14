<template>
  <div class="w-full h-screen">
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
    name: "Fundraisers",
    path: "/eventManagement/fundraisers",
  },
  {
    name: "Service Project",
    path: "/eventManagement/serviceProject",
  },
];
</script>

<style lang="scss" scoped></style>
