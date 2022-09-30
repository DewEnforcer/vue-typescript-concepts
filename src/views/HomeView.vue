<template>
  <div>
    <button @click="handleOrderAction('location')">Order by title</button>
    <JobList :jobs="jobs" :order="order" />
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
import Job from "../types/Job";
import OrderAction from "../types/OrderAction";
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

    const order = ref<OrderAction>("salary");

    const handleOrderAction = (actionType: OrderAction) => {
      order.value = actionType;
    }

    return {jobs, order, handleOrderAction}
  },
});
</script>
