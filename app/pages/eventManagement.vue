<template>
  <div class="w-full h-screen overflow-y-scroll flex flex-col">
    <button class="self-start p-2 bg-blue-100 rounded-xl">Create Event</button>
    <div class="filters">
      <div class=""></div>
    </div>
    <div class="w-full flex flex-col items-center h-fit gap-2">
      <events-card v-for="hi in eventsTest" :event="hi" />
    </div>
  </div>
</template>

<script setup>
const filterTypes = ref([
  { name: "All" },
  { name: "Volunteer Event" },
  { name: "Fundraiser" },
  { name: "Service Project" },
]);
const eventsTest = ref([
  { name: "rando event", type: "Fundraiser" },
  { name: "hi", type: "Fundraiser" },
  { name: "llallalal", type: "Volunteer Event" },
  { name: "jarvis a bum", type: "Service Project" },
]);
</script>

<style lang="scss" scoped></style>
