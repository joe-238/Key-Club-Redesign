<template>
  <div class="w-[80%] bg-red-100 p-2 border-[1px] border-gray-500">
    <i class="fa-solid fa-pen-to-square"></i>
    <h2 class="font-bold">{{ props.event.name }}</h2>
    <h3>{{ props.event.type }}</h3>
    <button class="p-2 bg-blue-600 w-full rounded-lg">View Event</button>
  </div>
</template>

<script setup>
const props = defineProps({
  event: {
    type: Object,
    required: true,
  },
});
</script>

<style scoped></style>
