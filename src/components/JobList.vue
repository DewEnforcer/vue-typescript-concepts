<template>
    <div>
        <div v-for="job in jobs" :key="job.id" class="job-item">
            <span>{{job.title}}</span>
            <span>{{job.location}}</span>
            <span>{{job.salary}}</span>
        </div>
    </div>
</template>

<script lang="ts"> //tsvue
import Job from '@/types/Job'
import { defineComponent, PropType } from 'vue'

export default defineComponent({
    props: {
        jobs: {
            required: true,
            type: Array as PropType<Job[]>
        }
    },
})
</script>
