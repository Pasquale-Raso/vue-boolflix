<template>
  <div>
    <div v-for="produzione in produzioni" :key="produzione.id">
      {{ produzione.name }}
    </div>
  </div>
</template>

<script>
export default {
  name: "Main",
  props: {
    produzioni: Array,
  },
};
</script>

<style>
</style>