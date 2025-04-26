<script setup>
import { ref, onMounted } from "vue";

// reactive state
const count = ref(0);
const newTask = ref("");
const tasks = ref([]);

const books = ref([
  { id: 1, title: "The Great Gatsby" },
  { id: 2, title: "To Kill a Mockingbird" },
  { id: 3, title: "1984" },
]);
const increment = () => {
  count.value++;
};

const addTask = async () => {
  if (!newTask.value) return;

  try {
    const response = await fetch("https://jsonplaceholder.typicode.com/todos");
    const data = await response.json();
    tasks.value = data.map((task) => ({
      id: task.id,
      title: task.title,
    }));
  } catch (e) {
    console.error("Error fetching data:", e);
  }
};

// lifecycle hooks
onMounted(() => {
  console.log(`The initial count is ${count.value}.`);
});
</script>

<template>
  <button @click="increment" class="bg-green-500 p-4 rounded text-white">
    Count is: {{ count }}
  </button>

  <form @submit.prevent="addTask" class="mt-4">
    <label for="newTask">Add task</label>
    <input
      type="text"
      v-model="newTask"
      id="newTask"
      name="newTask"
      placeholder="Enter a task"
      class="border p-2 ml-2"
    />
    <button type="submit" class="bg-blue-500 text-white px-4 py-2 ml-2 rounded">
      Add
    </button>
  </form>

  <div class="">
    <h3 class="">Books list</h3>
    <ul class="mt-4">
      <li v-for="book in books" :key="book.id">{{ book.title }}</li>
    </ul>
  </div>
  <!-- <h2>Tasks</h2>
  <ul class="mt-4">
    <li v-for="task in tasks" :key="task.id">
      {{ task.title }} -->

  <!-- </li>
  </ul> -->
</template>
