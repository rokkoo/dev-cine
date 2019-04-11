<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <hooper :progress="true" :itemsToShow="1.25" :centerMode="true">
      <slide>
        <div class="peli">sss</div>
      </slide>
      <slide>
        <div class="peli2">sss</div>
      </slide>
      <slide>slide 3</slide>
      <slide>slide 4</slide>
      <slide>slide 5</slide>
      <slide>slide 6</slide>
      <hooper-navigation slot="hooper-addons"></hooper-navigation>
    </hooper>
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
import { Hooper, Slide, Pagination as HooperPagination } from 'hooper';
import 'hooper/dist/hooper.css';

export default {
  name: 'HomePage',
  props: {
    msg: String,
  },
  components: {
    Hooper,
    Slide,
    HooperPagination,
  },
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

.peli {
  background-color: goldenrod;
  height: 100%;
}
.peli2 {
  background-color: tomato;
  height: 100%;
}
</style>
