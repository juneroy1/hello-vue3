<template>
  <div class="job-list">
    <ul>
        <li v-for="job in jobs" :key="job.id">
            <h2>{{ job.title }} in {{ job.location }}</h2>
            
        </li>
    </ul>
  </div>
</template>

<script lang="ts">
import Job from "@/types/Job";
import { defineComponent, PropType } from "vue";

export default defineComponent({
    props: {
        jobs: {
            required: true,
            type: Array as PropType<Job[]>,
        }
    },
  setup() {
    return {};
  },
});
</script>

<style scoped></style>
