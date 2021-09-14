<template>
  <div class="container container_main">
    <h1 v-if="results.length" class="text-center mt-2">FILM</h1>
    <div class="row">
      <div class="d-flex flex-wrap col-12 col-sm-4 col-md-10 col-lg-12 m-2">
        <div v-for="result in results" :key="result.id">
          <Card :item="result" />
        </div>
      </div>
    </div>

    <!-- _____________________Serie________________________ -->

    <h1 v-if="tvResults.length" class="text-center mt-2">SERIE</h1>
    <div class="row">
      <div class="d-flex flex-wrap col-12 col-sm-4 col-md-10 col-lg-12 m-2">
        <div v-for="tvResult in tvResults" :key="tvResult.id">
          <Card :item="tvResult" />
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
  props: ["results", "tvResults"],
};
</script>

<style scoped lang="scss">
.container_main {
  max-width: 1200px;
  margin: 0 auto;
}
</style>