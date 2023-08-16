<template>
  <div class="app">
    <!-- using data binding we are calling the prop (jobs) and set it equal to jobs data that was returned earlier  -->
    <JobList :jobs="jobs" />
  </div>
</template>
 

<script lang="ts">
// reactive gets imported automatically
import { defineComponent, reactive, ref, toRefs } from 'vue';
import JobList from './components/JobsList.vue'; 

import Job from "./types/Job";  

export default defineComponent({
  name: 'App',
  components: { JobList },
  setup() { 
    const jobs = ref<Job[]>([
      { title: 'Farm worker', location: 'ion Ranch', salary: 40000, id: '1' },
      { title: 'Fullstack Developer', location: 'Alabama', salary: 120000, id: '2' },
      { title: 'Swimming Teacher', location: 'punjabi valley', salary: 25000, id: '3' },
    ]);
    return { jobs }; 
  }
});
</script>

<style>

</style>
