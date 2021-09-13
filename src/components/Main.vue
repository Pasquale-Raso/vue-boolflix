<template>
  <div>
    <div v-for="mainApi in mainApis" :key="mainApi.id">
      {{ this.mainApi[0].title }}
    </div>
  </div>
</template>

<script>
export default {
  name: "Main",
  props: ["mainApi"],
  data() {
    return {};
  },
  methods: {},
};
</script>

<style scoped lang="scss">
</style>