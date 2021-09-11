<template>
  <div id="app">
    <Header @risultatoDiSearchInHeader="getRisultatoDiSearchInAppVue" />
    <Main />
    <!-- <Main :produzioni="produzioni" /> -->
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
      risultatoDiSearchInAppVue: [],

      // produzioni: [],
    };
  },
  methods: {
    getRisultatoDiSearchInAppVue(RisultatoDiSearchInAppVue) {
      this.risultatoDiSearchInHeader = RisultatoDiSearchInAppVue;
      console.log("Riusltato di app.vue", RisultatoDiSearchInAppVue);
    },
  },
};
</script>

<style lang="scss">
@import "./sass/File.scss";
</style>
