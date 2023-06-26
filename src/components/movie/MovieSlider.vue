<template>
  <section class="movie__slider">
    <swiper
      effect="coverflow"
      grab-cursor="true"
      centered-slides="true"
      slides-per-view="5"
      initial-slide="3"
      :autoplay="{ delay: 5000, disableOnInteraction: false }"
      :coverflow-effect="{
        rotate: 50,
        stretch: 0,
        depth: 100,
        modifier: 1,
        slideShadows: true,
      }"
      pagination
      class="mySwiper"
    >
      <swiper-slide v-for="(movie, index) in movies" :key="index">
        <img
          :src="`https://image.tmdb.org/t/p/w500/${movie.poster_path}`"
          :alt="movie.title"
        />
      </swiper-slide>
    </swiper>
  </section>
</template>

<script>
import { Swiper, SwiperSlide } from "swiper/vue";

export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  props: {
    movies: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style scoped>
.movie__slider {
  margin-bottom: 50px;
}
@import "swiper/css";
@import "swiper/css/effect-coverflow";
@import "swiper/css/pagination";
</style>
