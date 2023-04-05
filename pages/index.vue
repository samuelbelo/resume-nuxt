<template>
    <div class="container mx-auto px-8">
        <Navbar />
        <Hero/>
    </div>
</template>
<script setup>
import Hero from "~/components/main/Hero.vue";
import Navbar from "~/components/common/Navbar.vue";

definePageMeta({
    colorMode: 'dark',
})
</script>

<style scoped>

</style>