<script setup>
import { ref, onMounted } from "vue";
import Hero from "./components/Hero.vue";
import Navbar from "./components/Navbar.vue";
import Homecards from "./components/Homecards.vue";
</script>

<template>
  <Navbar />
  <Hero />
  <Homecards />
</template>
