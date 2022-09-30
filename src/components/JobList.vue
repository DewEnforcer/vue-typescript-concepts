<template>
    <div>
        <div v-for="job in sortedJobs" :key="job.id" class="job-item">
            <span>{{job.title}}</span>
            <span>{{job.location}}</span>
            <span>{{job.salary}}</span>
        </div>
    </div>
</template>

<script lang="ts"> //tsvue
import Job from '@/types/Job'
import OrderAction from '@/types/OrderAction'
import { computed, defineComponent, PropType } from 'vue'

export default defineComponent({
    props: {
        jobs: {
            required: true,
            type: Array as PropType<Job[]>
        },
        order: {
            required: true,
            type: String as PropType<OrderAction>
        }
    },
    setup(props) {
        const sortedJobs = computed(() => {
            return [...props.jobs].sort((a: Job, b: Job) => {
                return a[props.order] > b[props.order] ? 1 : -1;
            } );
        })

        return {sortedJobs};
    },
})
</script>
