<template>
  <div>
    <button @click="handleClick('title')">Orde by title</button>
    <button @click="handleClick('salary')">Order by salary</button>
    <button @click="handleClick('location')">Order by location</button>
    <JobList :jobs="jobs" :order="order"></JobList>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
import JobList from './components/JobList.vue';
import Job from "./types/Job";
import OrderTerm from '@/types/OrderTerm';
export default defineComponent({
  name: "App",
  components: { JobList},
  setup() {
    const jobs = ref<Job[]>([
      {
        title: "Farm Work",
        location: "lon lon ranch",
        salary: 3000,
        id: 1,
      },
      {
        title: "Engineer",
        location: "NY",
        salary: 3000,
        id: 1,
      },
      {
        title: "Soccer player",
        location: "Barcelona",
        salary: 30000000,
        id: 1,
      },
    ]);

    const order = ref<OrderTerm>('title');

    const handleClick = (term: OrderTerm) => {
      order.value = term;
    };

    return { jobs, handleClick, order }
  },
});
</script>

<style>
header {
  text-align: center;
}

header .order {
  margin-top: 20px;
}

button {
  margin: 0 10px;
  color: #1195c9;
  background: #d5f0ff;
  padding: 8px 16px;
  border-radius: 4px;
  cursor: pointer;
  font-weight: bold;
}
</style>
