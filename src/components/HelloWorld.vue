<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      For a guide and recipes on how to configure / customize this project,
      <br>check out the
      <a
        href="https://cli.vuejs.org"
        target="_blank"
        rel="noopener"
      >vue-cli documentation</a>.
    </p>
    <h3>Installed CLI Plugins</h3>
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
export default {
  name: "HelloWorld",
  props: {
    msg: String
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
</style>
