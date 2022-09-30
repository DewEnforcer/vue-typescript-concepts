<template>
  <div>
    <JobList :jobs="jobs" />
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
import Job from "../types/Job";
import JobList from "../components/JobList.vue";

export default defineComponent({
  name: 'HomeView',
  components: {
      JobList
  },
  setup() {
    const jobs = ref<Job[]>([
      {
        title: "webdev",
        location: "Brno",
        salary: "Many moneys",
        id: "1234-ABCD"
      },
      {
        title: "backend dev",
        location: "Brno",
        salary: "Many moneys++",
        id: "1234-EFGH"
      },
    ]);

    return {jobs}
  },
});
</script>
