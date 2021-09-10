<template>
  <div id="app">
    <Header />
    <Main :produzioni="produzioni" />
  </div>
</template>

<script>
import axios from "axios";
import Header from "@/components/Header.vue";
import Main from "@/components/Main.vue";
export default {
  data() {
    return {
      produzioni: [],
    };
  },
  name: "App",
  components: {
    Header: Header,
    Main: Main,
  },
  created() {
    axios
      .get(
        "https://api.themoviedb.org/3/movie/550?api_key=1c48c3a20a3d03674636d8f324d2b42d"
      )
      .then((res) => {
        console.log(res.data.production_companies);
        this.produzioni = res.data.production_companies;
      });
  },
};
</script>

<style lang="scss">
@import "./sass/File.scss";
</style>
