<template>
  <nav class="w-[15%] h-screen flex flex-col pt-10 items-center bg-green-100">
    <div class="flex flex-col gap-2 w-full">
      <h2 class="font-bold text-xl cursor-pointer mb-4 self-center">
        KEY CLUB
      </h2>
      <NuxtLink
        v-for="link in navLinks.find((l) => l.category === category).links"
        :class="
          link.type === 'btn'
            ? '  py-2 bg-blue-600 text-white font-semibold rounded-lg hover:bg-blue-700 transition-colors duration-200'
            : '  p-2 w-full text-blue-800 font-semibold rounded-lg hover:bg-blue-200 transition-colors duration-200'
        "
        :key="link.name"
        :to="link.redirect"
        ><i v-if="link.icon" class="fa-solid" :class="link.icon"></i>
        {{ link.name }}
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
      { redirect: "/", name: "Home", icon: "fa-home" },
      { redirect: "/about", name: "About", icon: "fa-address-card" },
      { redirect: "/contact", name: "Contact Us", icon: "fa-phone" },
      { redirect: "/login", name: "Log In", icon: "fa-right-to-bracket" },
      { redirect: "/signup", name: "Sign Up", type: "btn" },
    ],
  },
  {
    category: "student",
    links: [
      { redirect: "/", name: "Home", icon: "fa-home" },
      { redirect: "/events", name: "Events", icon: "fa-calendar" },
    ],
  },
  {
    category: "admin",
    links: [
      { redirect: "/", name: "Home", icon: "fa-home" },
      {
        redirect: "/eventManagement",
        name: "Event Management",
        icon: "fa-calendar",
      },
      {
        redirect: "/studentCharter",
        name: "Student Charter",
        icon: "fa-person",
      },
    ],
  },
];
</script>

<style scoped></style>
