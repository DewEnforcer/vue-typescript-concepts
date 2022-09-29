<template>
  <h1>Hi</h1>
  <span>{{name}} - {{age}}</span>
  <button type="button" @click="changeName('MyName')">Change name</button>
  <button type="button" @click="changeAge('25')">Change age</button>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';

export default defineComponent({
  name: 'HomeView',
  components: {
    
  },
  setup() {
      const name = ref("Link");
      const age = ref<number | string | null>(30);

      const changeName = (nameArg: string) => {
        name.value = nameArg;
      }
      const changeAge = (ageArg: string | number) => {
        age.value = ageArg;
      }

      return {name, age, changeName, changeAge}
  },
});
</script>
