<template>
  <div
    class="w-full h-screen bg-white flex flex-col items-center pt-10 overflow-y-scroll"
  >
    <h1 class="w-[80%] font-bold text-2xl mb-5">Student Charter</h1>
    <div class="w-[80%] flex justify-between">
      <div
        class="flex gap-2 justify-center items-center border-2 rounded-full px-2 py-1 w-fit"
      >
        <i class="fa-solid fa-magnifying-glass"></i>
        <input
          type="text"
          placeholder="Search"
          class="outline-none w-auto min-w-[150px] placeholder-gray-400"
          v-model="filter"
        />
      </div>
      <div class="w-fit flex items-center space-x-2">
        <div class="flex flex-wrap gap-2">
          <span
            class="flex items-center border-2 border-blue-500 text-gray-800 rounded-full px-3 py-1 text-sm"
          >
            Sort by: New Employees
            <button class="ml-2 font-bold text-blue-500 hover:text-gray-700">
              ✕
            </button>
          </span>
        </div>

        <div class="flex items-center space-x-2 cursor-pointer">
          <div class="flex flex-col items-center justify-between h-3 w-4">
            <span class="block h-[2px] w-full bg-gray-600 rounded"></span>
            <span class="block h-[2px] w-3/4 bg-gray-600 rounded"></span>
            <span class="block h-[2px] w-1/2 bg-gray-600 rounded"></span>
          </div>
          <h2 class="text-gray-800 font-medium">More Filters</h2>
        </div>
      </div>
    </div>
    <div class="flex items-center justify-between w-[80%] py-3 px-4">
      <div class="flex items-center w-1/4 space-x-3">
        <h2 class="font-medium text-gray-800 truncate">Name</h2>
      </div>
      <div class="w-1/5 text-gray-600 font-medium">Osis</div>
      <div class="w-1/5 text-gray-700 font-medium">Service Hours</div>
      <div class="w-1/5 text-gray-700 font-medium">Paid dues</div>
    </div>
    <div
      class="w-[80%] h-fit flex flex-col items-center justify-center rounded-xl"
    >
      <studentCharterCard
        v-for="student in filteredStudents"
        :key="student.osis"
        :student="student"
      ></studentCharterCard>
    </div>
  </div>
</template>

<script setup>
import studentCharterCard from "~/components/studentCharterCard.vue";
const filter = ref("");
const filteredStudents = computed(() => {
  if (!filter.value) return students.value;
  const nameLower = filter.value.toLowerCase();
  return students.value.filter(
    (student) =>
      student.name.toLowerCase().includes(nameLower) ||
      student.osis.toString().includes(nameLower)
  );
});

const students = ref([
  { name: "Josephine Liu", osis: 123456789, hours: 10, paid: true },
  { name: "Johnny Tang", osis: 987654321, hours: 5, paid: true },
  { name: "Thomas Jiang", osis: 234567891, hours: 0, paid: true },
  { name: "Ken Lin", osis: 345678912, hours: 4, paid: false },
  { name: "Emily Chen", osis: 456789123, hours: 12, paid: true },
  { name: "Michael Wong", osis: 567891234, hours: 8, paid: false },
  { name: "Sophia Lee", osis: 678912345, hours: 6, paid: true },
  { name: "Daniel Kim", osis: 789123456, hours: 3, paid: false },
  { name: "Grace Park", osis: 891234567, hours: 9, paid: true },
  { name: "Ethan Lin", osis: 912345678, hours: 2, paid: false },
  { name: "Olivia Zhang", osis: 135792468, hours: 7, paid: true },
  { name: "William Li", osis: 246813579, hours: 1, paid: false },
  { name: "Ava Chen", osis: 357924681, hours: 4, paid: true },
  { name: "James Liu", osis: 468135792, hours: 0, paid: false },
  { name: "Isabella Wong", osis: 579246813, hours: 11, paid: true },
  { name: "Benjamin Kim", osis: 681357924, hours: 5, paid: true },
  { name: "Mia Park", osis: 792468135, hours: 6, paid: false },
  { name: "Alexander Lee", osis: 813579246, hours: 3, paid: true },
  { name: "Charlotte Lin", osis: 924681357, hours: 9, paid: false },
  { name: "Henry Chen", osis: 147258369, hours: 2, paid: true },
  { name: "Amelia Wong", osis: 258369147, hours: 8, paid: false },
  { name: "Lucas Kim", osis: 369147258, hours: 4, paid: true },
  { name: "Ella Park", osis: 471369258, hours: 7, paid: true },
  { name: "Noah Lee", osis: 582471369, hours: 0, paid: false },
]);
</script>

<style scoped></style>
