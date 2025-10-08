<template>
  <div class="w-full md:w-1/6 rounded-md p-1">
    <ul class="flex flex-row flex-wrap gap-2">
      <li
        v-for="subpage in pages"
        :key="subpage.path"
        class="p-2 border-b border-white"
      >
        <NuxtLink
          :to="subpage.path"
          :class="[
            'text-sm lg:text-md block transition duration-300 ease-in-out',
            subpage.name === active
              ? 'text-blue-400'
              : 'text-black hover:text-blue-400',
          ]"
        >
          {{ subpage.name }}
        </NuxtLink>
      </li>
    </ul>
  </div>
</template>

<script setup>
defineProps({
  pages: Array,
  active: String,
});
</script>

<style scoped></style>
