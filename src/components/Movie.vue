<template>
  <section>
    <div class="card">
      <img :src="`${movie.posterPath}`">
      <div class="content">
        <h3>{{movie.title}}</h3>
        <p>{{movie.overview | overview}}</p>
        <p class="seeMore" v-if="moreInfo(movie.overview)">Ver más...</p>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Movie',
  props: {
    movie: {
      type: Object,
      required: true,
    },
  },
  data() {
    return {
      seeMore: false,
    };
  },
  filters: {
    overview(text) {
      const maxLength = 210;
      return text.length > maxLength ? text.substring(0, maxLength) : text;
    },
  },
  methods: {
    moreInfo(text) {
      const maxLength = 210;
      return text.length > maxLength;
    },
  },
};
</script>

<style lang="scss" scoped>
$mainColor: #2c3e50;

section {
  display: grid;
}
.card {
  display: grid;
  grid-template-columns: 0.5fr 1fr;
  margin: 1rem 1rem;
  width: 50%;
  box-shadow: 0 16px 38px -12px rgba(0, 0, 0, 0.56),
    0 4px 25px 0px rgba(0, 0, 0, 0.12), 0 8px 10px -5px rgba(95, 64, 64, 0.2);
  border-radius: 3px;
  background-color: #f1f1e6;
  text-align: center;
}

.content {
  padding: 1rem 1rem;
  align-self: center;
}

img {
  border-radius: 3px;
}
h3 {
  color: $mainColor;
}
.seeMore {
  color: tomato;
  cursor: pointer;
}
</style>
