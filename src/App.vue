<template>
  test
  {{ name }}
  {{ age }}
  <button @click="changeName('jq dev')">change name</button>
  <button @click="changeAge('24')">change name</button>
</template>

<script lang="ts">
import { defineComponent, reactive, ref, toRefs } from "vue";
// let age: string | number = 25
export default defineComponent({
  name: "App",
  components: {},
  setup() {
    // const state = reactive({
    //   name: 'jq dev',
    //   age: 25 as string | number
    // })

    // return {...toRefs(state)}

    const name = ref<string>("juneroy");
    const age = ref<number | string>(25);

    return { name, age };
  },
  //  data(){
  //   return {
  //     name: 'Jq',
  //     age: 25 as string | number,
  //   }
  //  },
  methods: {
    changeName(name: string) {
      this.name = name;
    },
    changeAge(age: string | number) {
      this.age = age;
    },
  },
});
</script>
