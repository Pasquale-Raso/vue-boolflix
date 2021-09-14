<template>
  <div>
    <div class="boxCard overflow-auto text-center m-2">
      <img
        class="img w-100"
        :src="`https://image.tmdb.org/t/p/w342/${item.poster_path}`"
      />
      <div class="d-none box-info p-3">
        <h3>{{ item.title }}</h3>
        <h6>{{ item.original_title }}</h6>
        <img
          class="bandiere"
          v-if="this.bandiere.includes(item.original_language)"
          :src="getbandiere(item.original_language)"
        />
        <span v-else>{{ item.original_language }}</span>
        <div>
          <i
            v-for="(star, index) in 5"
            :key="index"
            class="fas fa-star m-1 mt-3"
            :class="stelle(index, item.vote_average) ? 'colorgiallo' : ''"
          ></i>
          <span class="m-3">({{ item.vote_average }})</span>
        </div>
        <h6 class="overflow-hidden">{{ item.overview }}</h6>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "card",
  props: ["item"],
  components: {},
  data() {
    return {
      bandiere: ["en", "it", "de", "fr", "es"],
    };
  },
  methods: {
    getbandiere(lang) {
      return require(`@/assets/${lang}.png`);
    },
    stelle(index, voto) {
      const media = Math.ceil(voto / 2);
      if (media > index) {
        return true;
      }
    },
  },
};
</script>

<style scoped lang="scss">
.boxCard {
  background-color: black;
  width: 342px;
  height: 513px;
  color: white;
  border-radius: 10px;
  .img {
    width: 100%;
    border-radius: 10px;
  }
  &:hover {
    .img {
      display: none;
    }
    .box-info {
      display: block !important;
    }
  }
}
.bandiere {
  width: 50px;
  height: auto;
  margin-top: 10px;
}
.colorgiallo {
  color: gold;
}
</style>