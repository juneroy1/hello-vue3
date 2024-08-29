<template>
  <div></div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
    props: {
        jobs: {
            required: true,
            type: Array,
        }
    },
  setup() {
    return {};
  },
});
</script>

<style scoped></style>
