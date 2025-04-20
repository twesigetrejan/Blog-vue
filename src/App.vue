<script setup>
import { ref, onMounted } from "vue";

// reactive state
const count = ref(0);

const increment = () => {
  count.value++;
};
// lifecycle hooks
onMounted(() => {
  console.log(`The initial count is ${count.value}.`);
});
</script>

<template>
  <button @click="increment" className="bg-green-500 p-10">
    Count is: {{ count }}
  </button>
</template>
