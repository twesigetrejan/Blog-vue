<script setup>
import { ref } from "vue";

const name = ref("Trejan_dev");
const channel = ref("YouTube");
const hack = onclick(() => {
  alert("You clicked me!");
});
</script>

<template>
  <header>
    <!-- <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" /> -->
    <h1 class="bg-red-400 flex">Hello {{ name }}</h1>
    <h2 v-text="channel"></h2>
    <h3 v-text="hack"></h3>
    <!-- <div class="wrapper">
      <HelloWorld msg="You did it well!" />
    </div> -->
  </header>

  <!-- <main>
    <TheWelcome />
  </main> -->
</template>

<style scoped></style>
