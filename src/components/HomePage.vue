<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <SliderItems :movies="movies"/>
    <Seats/>
  </div>
</template>

<script>
import SliderItems from './Slider.vue';
import Seats from './Seats.vue';

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

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
body {
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
