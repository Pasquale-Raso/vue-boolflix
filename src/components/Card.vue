<template>
  <div class="card" style="width: 18rem">
    <div class="card-body">
      <h5>Titolo:{{ cardApi }}</h5>
      <h6>Titolo Originale:</h6>
      <h6>Lingua:</h6>
      <h6>Voto:</h6>
    </div>
  </div>
</template>

<script>
export default {
  name: "card",
  props: ["cardApi"],
};
</script>

<style>
</style>