<template>
  <header>
    <div class="d-flex justify-content-between align-items-center mx-4">
      <p>BOOLFLIX</p>
      <div class="align-items-center d-flex mb-3">
        <input
          @keyup.enter="search"
          v-model="testoUtente"
          type="text"
          placeholder="Cerca..."
          class="search-box"
        />
        <button type="button" class="bottone">Cerca</button>
      </div>
    </div>
  </header>
</template>

<script>
import axios from "axios";
export default {
  name: "Header",
  data() {
    return {
      risultatoDiSearchInHeader: [],
      testoUtente: "",
      baseUri: "https://api.themoviedb.org/3/",
      typeSearch: "search/movie",
      apiKey: "?api_key=1c48c3a20a3d03674636d8f324d2b42d",
    };
  },
  methods: {
    search() {
      axios
        .get(
          `${this.baseUri}${this.typeSearch}${this.apiKey}&query=${this.testoUtente}`
        )
        .then((res) => {
          console.log("Riusltato dell'api", res.data.results);
          this.risultatoDiSearchInHeader = res.data.results;
          console.log(
            "Riusltato di Header.vue",
            this.risultatoDiSearchInHeader
          );

          // INVIO risultatoDiSearch AD APP.VUE
          this.$emit(
            "risultatoDiSearchInHeader",
            this.risultatoDiSearchInHeader
          );

          // this.produzioni = res.data.results;
        });
    },
  },
};
</script>

<style scoped lang="scss">
header {
  background-color: #000000;
  height: 70px;

  p {
    font-family: "Bebas Neue", cursive;
    color: red;
    font-size: 50px;
  }
  .search-box {
    width: 200px;
    height: 30px;
  }
  .bottone {
    background-color: #ff0000;
    border: none;
    color: white;
    height: 28px;
    width: 40px;
    text-align: center;
    display: inline-block;
    font-size: 12px;
    margin-left: 1px;
  }
}
</style>