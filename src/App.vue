<template>
 test
 <button @click="changeName('jq dev')">change name</button>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
// let age: string | number = 25
export default defineComponent({
  name: 'App',
  components: {
  },
   data(){
    return {
      name: 'Jq',
      age: 25 as string | number,
    }
   },
   methods:{
    changeName(name: string){
      this.name = name
    },
    changeAge(age: string){
      this.age = age
    }
   }
}); 
</script>

