<template>
  <div class="job-list">
    <p>Ordered by {{ order }}</p>
    <TransitionGroup name="list" tag="ul">
      <li v-for="job in orderedJobs" :key="job.id">
        <h2>{{ job.title }} in {{ job.location }}</h2>
        <div class="salary">
            <img src="../assets/php.svg" alt="php" width="100">
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
    </TransitionGroup>
  </div>
</template>

<script lang="ts">
import Job from "@/types/Job";
import OrderTerm from "@/types/OrderTerm";
import { computed, defineComponent, PropType, TransitionGroup } from "vue";

export default defineComponent({
  props: {
    jobs: {
      required: true,
      type: Array as PropType<Job[]>,
    },
    order: {
      required: true,
      type: String as PropType<OrderTerm>,
    },
  },
  setup(props) {

    const orderedJobs = computed(() => {
        return [...props.jobs].sort((a:Job,b:Job) => {
            return a[props.order] > b[props.order] ? 1: -1          
        }) 
    })



    return {orderedJobs};
  },
});
</script>

<style scoped>
.job-list{
    max-width: 960px;
    margin: 40px auto;
}
.job-list ul{
    padding: 0;
}

.job-list li{
    list-style-type: none;
    background: white;
    padding: 16px;
    margin: 16px 0;
    border-radius: 4px;
}

.job-list h2{
    margin: 0 0 10px;
    text-transform: capitalize;
}

.salary{
    display: flex;
}

.salary img{
    width: 30px;
}

.salary p{
    color: #17bf66;
    font-weight: bold;
    margin: 10px 4px;
}

.list-move {
    transition: all 1s;
}
 
</style>
