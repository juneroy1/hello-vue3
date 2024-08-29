<template>
  <div></div>
  <!-- test
  {{ name }}
  {{ age }}
  <button @click="changeName('jq dev')">change name</button>
  <button @click="changeAge('24')">change name</button> -->
</template>

<script lang="ts">
import { defineComponent, reactive, ref, toRefs } from "vue";
import Job from "./types/Job";
// let age: string | number = 25
export default defineComponent({
  name: "App",
  setup() {


    // const state = reactive({
    //   name: 'jq dev',
    //   age: 25 as string | number
    // })

    // return {...toRefs(state)}

    // const name = ref<string>("juneroy");
    // const age = ref<number | string>(25);

    // return { name, age };

    const jobs = ref<Job[]>([])
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
