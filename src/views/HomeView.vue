<template>
  <main>
    <SliderSection :attr="'slider__wrap cafe5'" />
    <IntroSection :attr="'intro__wrap container section'" />
    <PortSection :attr="'port__wrap section center'" />
    <MovieSection :attr="'movie__wrap cafe5 section'" />
    <YoutubehSection :attr="'youtube__wrap cafe5 section'" />
    <UnsplashSection :attr="'unsplash__wrap cafe5 section bg-blue'" />
  </main>
</template>

<script>
import IntroSection from "@/components/section/IntroSection.vue";
import SliderSection from "@/components/section/SliderSection.vue";
import MovieSection from "@/components/section/MovieSection.vue";
import PortSection from "@/components/section/PortSection.vue";
import YoutubehSection from "@/components/section/YoutubehSection.vue";
import UnsplashSection from "@/components/section/UnsplashSection.vue";

export default {
  components: {
    SliderSection,
    IntroSection,
    MovieSection,
    PortSection,
    YoutubehSection,
    UnsplashSection,
  },
};
</script>
