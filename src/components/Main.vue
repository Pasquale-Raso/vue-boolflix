<template>
  <div>
    <!-- <div v-for="produzione in produzioni" :key="produzione.id">
      {{ produzione.title }}
    </div> -->
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

<style scoped lang="scss">
</style>