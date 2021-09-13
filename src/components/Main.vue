<template>
  <div>
    <div>
      <Card :cardApi="mainApiforCard" />
    </div>
  </div>
</template>

<script>
import Card from "@/components/Card.vue";

export default {
  name: "Main",
  components: {
    Card: Card,
  },
  props: ["mainApi"],
  data() {
    return {
      mainApiforCard: [],
    };
  },
  methods: {
    getMeinApi(props, mainApi) {
      this.mainApiforCard = (props, mainApi);
    },
  },
};
</script>

<style scoped lang="scss">
</style>