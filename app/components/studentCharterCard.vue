<template>
  <div
    class="flex items-center justify-between w-full border-t bg-white border-gray-200 py-3 px-4 hover:bg-gray-50 transition"
  >
    <div class="flex items-center w-1/4 space-x-3">
      <h2 class="font-medium text-gray-800 truncate">
        {{ props.student.name }}
      </h2>
    </div>
    <div class="w-1/5 text-gray-600 text-sm">
      <h2 class="bg-gray-100 w-fit px-2 rounded-full">
        {{ props.student.osis }}
      </h2>
    </div>
    <div class="w-1/5 text-gray-700 text-sm">
      Total Volunteer Hours:
      <span class="font-medium text-blue-600">
        {{ props.student.hours }}
      </span>
    </div>
    <div class="w-1/5 flex items-center space-x-2">
      <button
        @click="togglePaid"
        class="relative inline-flex h-6 w-11 items-center rounded-full transition-colors duration-300 focus:outline-none"
        :class="isPaid ? 'bg-blue-500' : 'bg-gray-300'"
      >
        <span
          class="inline-block h-5 w-5 transform rounded-full bg-white transition-transform duration-300"
          :class="isPaid ? 'translate-x-5' : 'translate-x-1'"
        ></span>
      </button>

      <span
        class="font-medium text-sm"
        :class="isPaid ? 'text-blue-600' : 'text-gray-500'"
      >
        {{ isPaid ? "Paid" : "Unpaid" }}
      </span>
    </div>
  </div>
</template>

<script setup>
import { ref, watch } from "vue";
const props = defineProps({
  student: {
    type: Object,
    required: true,
  },
});

const emit = defineEmits(["update:paid"]);
const isPaid = ref(props.student.paid);

watch(
  () => props.student.paid,
  (newValue) => {
    console.log("Prop changed:", newValue);
    isPaid.value = newValue;
  }
);

function togglePaid() {
  isPaid.value = !isPaid.value;
  console.log("Toggled value:", isPaid.value);
  emit("update:paid", isPaid.value);
}
</script>

<style scoped></style>
