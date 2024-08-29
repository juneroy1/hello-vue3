<template>
 test
 <button @click="changeName('jq dev')">change name</button>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'App',
  components: {
  },
   data(){
    return {
      name: 'Jq'
    }
   },
   methods:{
    changeName(name: string){
      this.name = name
    }
   }
}); 
</script>

