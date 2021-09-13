<template>
  <div>
    <div class="boxCard text-center m-2">
      <div>{{ item.title }}</div>
      <div>{{ item.original_title }}</div>
      <div>{{ item.original_language }}</div>
      <div>{{ item.vote_average }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "card",
  props: ["item"],
};
</script>

<style scoped lang="scss">
.boxCard {
  background-color: black;
  width: 300px;
  height: 500px;
  color: white;
  border-radius: 10px;
}
</style>