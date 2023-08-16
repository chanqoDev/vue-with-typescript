<template>
  <div class="app">
    <header>
      <div class="order">
        <button @click="handleClick('title')">order by title</button>
        <button @click="handleClick('salary')">order by Salary</button>
        <button @click="handleClick('location')">order by location</button>
        <JobList :jobs="jobs" :order="order" />
      </div>
    </header>
  </div>
</template>
 

<script lang="ts">
// reactive gets imported automatically
import { defineComponent, reactive, ref, toRefs } from 'vue';
import JobList from './components/JobsList.vue'; 
import OrderTerm from "./types/OrderTerm"; 
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
    const order = ref<OrderTerm>('title'); 
    const handleClick = (term: OrderTerm ) => {
      order.value = term; 
    }
    return { jobs, handleClick, order}; 
  }
});
</script>

<style>
header {
  text-align: center;
}
header .order {
  margin-top: 20px; 
}
button{
  margin: 0 10px; 
  color: blue; 
  border: 3px solid dodgerblue; 
  background: whitesmoke; 
  padding: 8px 15px; 
  border-radius: 4px;
  cursor: pointer;
  font-weight: bold;
}
</style>
