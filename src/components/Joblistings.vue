<script setup>
import jobData from "@/jobs.json";
import { ref } from "vue";
import JobLisiting from "./JobLisiting.vue";
const jobs = ref(jobData);
// console.log(jobs.value);
</script>

<template>
  <section class="bg-blue-50 px-4 py-10">
    <div class="contaner-xl lg:container m-auto">
      <h2 class="h2 text-3xl font-bold text-green-500 mb-6 text-center">
        Browse Jobs
      </h2>
      <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
        <JobLisiting v-for="job in jobs" :key="job.id" :job="job" />
      </div>
    </div>
  </section>
</template>
