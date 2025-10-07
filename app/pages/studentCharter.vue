<template>
    <div class="w-full min-h-screen h-fit flex flex-col items-center justify-center">
        <h1 class="">Student Charter</h1>
        <div class="w-[80%] h-fit flex flex-col items-center justify-center">
            <studentCharterCard></studentCharterCard>
        </div>
    </div>
</template>

<script setup>
import studentCharterCard from '~/components/studentCharterCard.vue';
const students = [
    {name: "Josephine Liu", osis: 1234444434432, hours: 10, paid: true},
    {name: "Johnny Tang", osis: 231231231231, hours: 1, paid: true},
    {name: "Thomas Jiang", osis: 21321312321321, hours: 0, paid: true},
    {name: "Ken Lin", osis: 1231231321, hours: 4, paid: false},
]
</script>

<style scoped>

</style>