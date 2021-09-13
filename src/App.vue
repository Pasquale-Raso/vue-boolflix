<template>
  <div id="app">
    <Header @headerApi="getApi" />
    <Main :results="appApi" />
  </div>
</template>

<script>
import Header from "@/components/Header.vue";
import Main from "@/components/Main.vue";
export default {
  name: "App",
  components: {
    Header: Header,
    Main: Main,
  },
  data() {
    return {
      appApi: [],
    };
  },
  methods: {
    getApi(headerApi) {
      this.appApi = headerApi;
    },
  },
};
</script>

<style lang="scss">
@import "./sass/File.scss";
</style>
