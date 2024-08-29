<template>
  <div>
    <button @click="handleClick('title')">order by title</button>
    <button @click="handleClick('salary')">order by salary</button>
    <button @click="handleClick('location')">order by location</button>
    <JobList
    :jobs="jobs"
    :order="order"
    />
  </div>
  <!-- test
  {{ name }}
  {{ age }}
  <button @click="changeName('jq dev')">change name</button>
  <button @click="changeAge('24')">change name</button> -->



</template>

<script lang="ts">
import { defineComponent, reactive, ref, toRefs } from "vue";
import Job from "./types/Job";
import OrderTerm from "./types/OrderTerm";
import JobList from "./components/JobList.vue";
// let age: string | number = 25
export default defineComponent({
  name: "App",
  components:{
    JobList
  },
  setup() {


    // const state = reactive({
    //   name: 'jq dev',
    //   age: 25 as string | number
    // })

    // return {...toRefs(state)}

    // const name = ref<string>("juneroy");
    // const age = ref<number | string>(25);

    // return { name, age };

    const jobs = ref<Job[]>([
      {title: 'jq', location: 'lon test', salary: 100.22, id: '1'},
      {title: 'jq2', location: 'lon test2', salary: 100.22111, id: '2'},
      {title: 'jq2', location: 'lon test2', salary: 100.22111, id: '3'},
      {title: 'jq2', location: 'lon test2', salary: 100.22111, id: '4'},
      {title: 'jq22', location: 'lon tes2t2', salary: 1020.22111, id: '5'}
    ])
    const order = ref<OrderTerm>('title');
    const handleClick = (term:OrderTerm) => {
      order.value = term
    }

    return {jobs, handleClick, order}
  },
  //  data(){
  //   return {
  //     name: 'Jq',
  //     age: 25 as string | number,
  //   }
  //  },
  // methods: {
  //   // changeName(name: string) {
  //   //   this.name = name;
  //   // },
  //   // changeAge(age: string | number) {
  //   //   this.age = age;
  //   // },
  // },
});
</script>
