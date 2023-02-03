<template>
  <div>
    <JobList :jobs="jobs"></JobList>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
import JobList from './components/JobList.vue';
import Job from "./types/Job";
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
    return { jobs }
  },
});
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
