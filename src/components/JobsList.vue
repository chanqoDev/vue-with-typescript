<template>
    <div class="job-list">
        <ul>
            <li v-for="job in jobs" :key="job.id"><h2>{{ job.title }} in {{ job.location }}</h2> <div class="salary"><p>{{ job.salary }} USD</p></div>
            <div class="description"> This is a good job for you to get started in passing props into the browser</div></li>
        </ul>
    </div>
</template>


<script lang="ts">
import { defineComponent, PropType } from 'vue';
import Job from "@/types/Job"; 

export default defineComponent({
    props: {
        jobs: {
            requried: true,
            type: Array as PropType<Job[]>
        }
    }
})
</script>

<style>
.job-list {
    max-width: 960px; 
    margin: 50px auto; 
}
.job-list ul{
    padding: 0; 
}
.job-list li {
    list-style-type: none; 
    background: white; 
    padding: 16px; 
    margin: 16px 0; 
    border-radius: 4px; 
}
.job-list h2 {
    margin: 0 0 10px; 
    text-transform: capitalize; 
}
.salary {display: flex}
.salary p {
    color: dodgerblue;
    font-weight: bold; 
    margin: 10px 5px; 
}
</style>