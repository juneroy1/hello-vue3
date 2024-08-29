<template>
  <div class="job-list">
    <ul>
      <li v-for="job in jobs" :key="job.id">
        <h2>{{ job.title }} in {{ job.location }}</h2>
        <div class="salary">
          <p>{{ job.salary }} PHP</p>
        </div>
        <div class="description">
          <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit.
            Necessitatibus vel et odio illo incidunt, amet voluptas dicta
            temporibus animi neque sit error deleniti rem dolor ipsa quas harum
            dolorem voluptates?
          </p>
        </div>
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
    },
  },
  setup() {
    return {};
  },
});
</script>

<style scoped></style>
