<template>
  <slider animation="fade" :autoplay="false">
    <slider-item v-for="(movie, index) in movies.movies" :key="index" class="slide">
      <section class="slideSection">
        <div class="movieInformation">
          <p>{{movie.title}}</p>
          <p class="popularity">{{movie.popularity}}</p>
          <!-- TODO: enlazar el nombre al btn -->
          <button>¡Comprar entrada!</button>
        </div>
        <img :src="`${movie.posterPath}`">
      </section>
    </slider-item>
  </slider>
</template>

<script>
import { Slider, SliderItem } from 'vue-easy-slider';

export default {
  name: 'sliderItems',
  props: {
    movies: Object,
  },
  components: {
    Slider,
    SliderItem,
  },
};
</script>

<style lang="scss" scoped>
.slider {
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
  margin-bottom: 2rem;

  > .slider-btn {
    color: #2c3e50 !important;
  }
}

.slide {
  color: white;
  display: grid;
  align-items: center;
  font-size: 2rem;
  height: 100%;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
  box-shadow: 0 16px 38px -12px rgba(0, 0, 0, 0.56),
    0 4px 25px 0px rgba(0, 0, 0, 0.12), 0 8px 10px -5px rgba(95, 64, 64, 0.2);
  > .slideSection {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    align-items: center;
    background-size: contain;
    background-repeat: no-repeat;
    background-position: right;
    margin-left: 2.5rem;
    margin-right: 2.5rem;

    > .movieInformation {
      justify-self: flex-end;

      > p {
        margin: 0;
      }

      > .popularity {
        // TODO: ver porque se mueve la fuente si cambiamos el tamaño
        font-size: 1rem;
      }

      > button {
        cursor: pointer;
        border: 1px solid rgba(27, 32, 35, 0.2);
        border-radius: 15px;
        display: inline-block;
        padding: 6px 12px;
        color: #24292e;
      }

      > button:not(:disabled) {
        background-image: linear-gradient(180deg, #f1f1e6, #fafbfc);
        box-shadow: rgba(0, 0, 0, 0.4) 0 1px 3px;
      }

      > button:disabled {
        background-color: #dde1e4;
        color: #6a7475;
      }
    }

    > img {
      height: 70%;
      border-radius: 10%;
      justify-self: flex-end;
      margin-right: 2rem;
    }
  }
}
</style>
