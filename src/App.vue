<template>
  <div>
    <header>
      <div class="title">
        <img src="./assets/php.svg" alt="php" width="100">
        <h1>Jq Jobs</h1>        
      </div>
      <div class="order">
        <button @click="handleClick('title')">order by title</button>
        <button @click="handleClick('salary')">order by salary</button>
        <button @click="handleClick('location')">order by location</button>
      </div>
    </header>
   
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
      {title: 'developer', location: 'Davao city', salary: 100000.00, id: '1'},
      {title: 'software engineer', location: 'Panabo city', salary: 200000.00, id: '2'},
      {title: 'mobile engineer', location: 'Iligan city', salary: 160000.00, id: '3'},
      {title: 'AI engineer', location: 'Buhangin agdao', salary: 300000.00, id: '4'},
      {title: 'Machine learning engineer', location: 'Unahan sa Panabo', salary: 400000.00, id: '5'}
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

<style>
header {
  text-align: center;
}
header .order {
  margin-top: 20px;
}
button{
  margin: 0 10px;
  color: #1195c9;
  border: 3px solid #1195c9;
  background: #d5f0ff;
  padding: 8px 16px;
  border-radius: 4px;
  cursor: pointer;
  font-weight: bold;
}
header .title{
  display: flex;
  justify-content: center;
}

header img {
  width: 60px;
  margin-right: 20px;
}

header h1 {
  font-size: 3em;
}
</style>
