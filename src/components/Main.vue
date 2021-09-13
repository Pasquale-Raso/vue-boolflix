<template>
  <div class="container container_main">
    <div class="row">
      <div class="d-flex flex-wrap col-12 col-sm-4 col-md-10 col-lg-12 m-2">
        <div v-for="result in results" :key="result.id">
          <Card :item="result" />
        </div>
      </div>
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
  props: ["results"],
};
</script>

<style scoped lang="scss">
.container_main {
  max-width: 1000px;
  margin: 0 auto;
}
</style>