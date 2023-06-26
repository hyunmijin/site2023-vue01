<template>
  <ContTitle title="unsplash" />
  <UnsplashSlider :sliderImages="sliderImages" />
  <UnsplashSearch @search="SearchImage" />
  <UnsplashTag @search="SearchImage" />
  <UnsplashCont :images="images" />
</template>

<script>
import ContTitle from "@/components/layout/ContTitle.vue";
import UnsplashSlider from "@/components/unsplash/UnsplashSlider.vue";
import UnsplashSearch from "@/components/unsplash/UnsplashSearch.vue";
import UnsplashTag from "@/components/unsplash/UnsplashTag.vue";
import UnsplashCont from "@/components/unsplash/UnsplashCont.vue";
import { ref } from "vue";

export default {
  components: {
    ContTitle,
    UnsplashSlider,
    UnsplashSearch,
    UnsplashTag,
    UnsplashCont,
  },

  setup() {
    const images = ref([]);
    const sliderImages = ref([]);

    const TopImages = async () => {
      await fetch(
        `https://api.unsplash.com/photos?client_id=xl3XdD26yx6VUDJS2flUAuj_0xNZpW0a_yfYiBdOX7Y&per_page=30`
      )
        .then((response) => response.json())
        .then((result) => {
          // console.log(result);
          console.log(result);
          images.value = result;
        })
        .catch((error) => console.log("error", error));
    };
    TopImages();

    const SearchImage = async (query) => {
      await fetch(
        `https://api.unsplash.com/search/photos?client_id=xl3XdD26yx6VUDJS2flUAuj_0xNZpW0a_yfYiBdOX7Y&per_page=30&query=${query}`
      )
        .then((response) => response.json())
        .then((result) => {
          images.value = result.results;
        })
        .catch((error) => console.log(error));
    };

    const SliderImages = () => {
      fetch(
        `https://api.unsplash.com/photos?client_id=xl3XdD26yx6VUDJS2flUAuj_0xNZpW0a_yfYiBdOX7Y&per_page=30`
      )
        .then((response) => response.json())
        .then((result) => {
          sliderImages.value = result.filter(
            (image) => image.width > image.height
          );
        })
        .catch((error) => console.log(error));
    };
    SliderImages();
    return {
      images,
      sliderImages,
      TopImages,
      SearchImage,
      SliderImages,
    };
  },
};
</script>
