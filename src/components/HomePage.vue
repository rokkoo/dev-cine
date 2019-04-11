<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <slider animation="fade" :autoplay="false">
      <slider-item v-for="(movie, index) in movies.movies" :key="index" class="slide">
        <section class="slideSection" :style="`background-image: url(${movie.posterPath})`">
          <h3>{{movie.title}}</h3>
        </section>
      </slider-item>
    </slider>
    <h4 v-if="loadingData">Cargando datos...</h4>
    <div class="map">
      <div class="row">
        <div class="seats">
          <div class="seat"></div>
          <div class="seat"></div>
          <div class="seat"></div>
        </div>

        <!-- <div class="space"></div> -->

        <div class="seats">
          <div class="seat"></div>
          <div class="seat"></div>
          <div class="seat"></div>
        </div>

        <!-- <div class="space"></div> -->

        <div class="seats">
          <div class="seat"></div>
          <div class="seat"></div>
          <div class="seat"></div>
        </div>
      </div>
      <div class="row">
        <div class="seats">
          <div class="seat"></div>
          <div class="seat"></div>
          <div class="seat"></div>
        </div>

        <!-- <div class="space"></div> -->

        <div class="seats">
          <div class="seat"></div>
          <div class="seat"></div>
          <div class="seat"></div>
        </div>

        <!-- <div class="space"></div> -->

        <div class="seats">
          <div class="seat"></div>
          <div class="seat"></div>
          <div class="seat"></div>
        </div>
      </div>
      <div class="row">
        <div class="seats">
          <div class="seat"></div>
          <div class="seat"></div>
          <div class="seat"></div>
        </div>

        <!-- <div class="space"></div> -->

        <div class="seats">
          <div class="seat"></div>
          <div class="seat"></div>
          <div class="seat"></div>
        </div>

        <!-- <div class="space"></div> -->

        <div class="seats">
          <div class="seat"></div>
          <div class="seat"></div>
          <div class="seat"></div>
        </div>
      </div>
      <div class="row">
        <div class="seats">
          <div class="seat"></div>
          <div class="seat"></div>
          <div class="seat"></div>
        </div>

        <!-- <div class="space"></div> -->

        <div class="seats">
          <div class="seat"></div>
          <div class="seat"></div>
          <div class="seat"></div>
        </div>

        <!-- <div class="space"></div> -->

        <div class="seats">
          <div class="seat"></div>
          <div class="seat"></div>
          <div class="seat"></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { Slider, SliderItem } from "vue-easy-slider";
import "hooper/dist/hooper.css";

export default {
  name: "HomePage",
  props: {
    msg: String
  },
  data: function() {
    return {
      movies: {},
      loadingData: true
    };
  },
  beforeMount() {
    this.fetchData();
  },
  components: {
    Slider,
    SliderItem
  },
  methods: {
    fetchData: async function() {
      this.loadingData = true;
      const fetchUrl = "http://localhost:3010/movies/cartelera";
      this.movies = await fetch(fetchUrl).then(data => data.json());
      this.loadingData = false;
    }
  },
  computed: {
    setBackGround: function(url) {
      console.log(url);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
body {
  display: flex;
  align-items: center;
  justify-content: center;
}

@import "./cinemaSeats.scss";

.slider {
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
  margin-bottom: 2rem;
}

.slide {
  color: #2c3e50;
  display: grid;
  align-items: center;
  font-size: 2rem;
  height: 100%;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);

  > .slideSection {
    background-size: contain;
    background-repeat: no-repeat;
    background-position: right;
    margin-left: 2.5rem;
    margin-right: 2.5rem;
  }
}
</style>
