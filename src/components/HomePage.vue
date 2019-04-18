<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <Slider-Items :movies="movies"/>
    <Seats v-if="false"/>
    <Movie v-for="(movie, index) in movies.movies" :key="index" :movie="movie"/>
  </div>
</template>

<script>
import SliderItems from './Slider.vue';
import Seats from './Seats.vue';
import Movie from './Movie.vue';

export default {
  name: 'HomePage',
  props: {
    msg: String,
  },
  data() {
    return {
      movies: {},
      loadingData: true,
    };
  },
  beforeMount() {
    this.fetchData();
  },
  components: {
    SliderItems,
    Seats,
    Movie,
  },
  methods: {
    async fetchData() {
      this.loadingData = true;
      const fetchUrl = 'http://localhost:3010/movies/cartelera';
      this.movies = await fetch(fetchUrl).then(data => data.json());
      this.loadingData = false;
    },
  },
  computed: {},
};
</script>

<style scoped lang="scss">
body {
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
