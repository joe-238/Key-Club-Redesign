<template>
  <nav class="w-full flex justify-between p-5 items-center bg-green-100">
    <div class="">
      <h2 class="font-bold text-xl cursor-pointer">SITHS KEY CLUB</h2>
    </div>
    <div class="flex gap-2">
      <NuxtLink
        v-for="link in navLinks.find((l) => l.category === category).links"
        :class="
          link.type === 'btn'
            ? 'px-4 py-2 bg-blue-600 text-white font-semibold rounded-lg hover:bg-blue-700 transition-colors duration-200'
            : 'px-4 py-2 text-blue-800 font-semibold rounded-lg hover:bg-blue-200 transition-colors duration-200'
        "
        :key="link.name"
        :to="link.redirect"
        >{{ link.name }}
      </NuxtLink>
    </div>
  </nav>
</template>

<script setup>
const category = ref("admin"); //public, student, admin
const navLinks = [
  {
    category: "public",
    links: [
      { redirect: "/", name: "Home" },
      { redirect: "/about", name: "About" },
      { redirect: "/contact", name: "Contact Us" },
      { redirect: "/login", name: "Log In" },
      { redirect: "/signup", name: "Sign Up", type: "btn" },
    ],
  },
  {
    category: "student",
    links: [
      { redirect: "/", name: "Home" },
      { redirect: "/events", name: "Events" },
    ],
  },
  {
    category: "admin",
    links: [
      { redirect: "/", name: "Home" },
      { redirect: "/eventmanage", name: "Event Management" },
      { redirect: "/studentsCharter", name: "Student Charter" },
    ],
  },
];
</script>

<style scoped></style>
