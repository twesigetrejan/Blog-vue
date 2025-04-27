<script setup>
import Hero from "./components/Hero.vue";
import Navbar from "./components/Navbar.vue";
import Homecards from "./components/Homecards.vue";
import Joblistings from "./components/Joblistings.vue";
</script>

<template>
  <Navbar />
  <Hero />
  <Homecards />
  <Joblistings :limit="3" :showButton="true" />
</template>
