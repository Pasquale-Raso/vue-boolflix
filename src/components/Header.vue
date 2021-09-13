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
        <button @click="search" type="submit" class="bottone">Cerca</button>
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
      rispApiTv: [],
      rispApi: [],
      testoUtente: "",
      baseUri: "https://api.themoviedb.org/3/",
      typeSearch: "search/movie",
      typeSearchTv: "search/tv",
      apiKey: "?api_key=1c48c3a20a3d03674636d8f324d2b42d",
    };
  },
  methods: {
    search() {
      // INVIO RICHIESTA AD API
      axios
        .get(
          `${this.baseUri}${this.typeSearch}${this.apiKey}&query=${this.testoUtente}`
        )
        .then((res) => {
          // console.log("Riusltato dell'API", res.data.results);
          this.rispApi = res.data.results;
          // console.log(
          //   "Riusltato di HEADER.vue",
          //   this.rispApi
          // );

          if (this.rispApi) this.$emit("headerApi", this.rispApi);

          // resetto tsto inserito da utente
          // this.testoUtente = "";
        });
      axios
        .get(
          `${this.baseUri}${this.typeSearchTv}${this.apiKey}&query=${this.testoUtente}`
        )
        .then((res) => {
          this.rispApiTv = res.data.results;

          if (this.rispApiTv) this.$emit("headerApiTv", this.rispApiTv);

          // resetto tsto inserito da utente
          // this.testoUtente = "";
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