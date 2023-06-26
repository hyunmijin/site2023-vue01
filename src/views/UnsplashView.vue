<template>
  <ContTitle title="unsplash" />
  <UnsplashSlider />
  <UnsplashSearch />
  <UnsplashTag @search="SearchImage" />
  <UnsplashCont :unsplash="unsplash" />
</template>

<script>
import ContTitle from "@/components/layout/ContTitle.vue";
import UnsplashSlider from "@/components/unsplash/UnsplashSlider.vue";
import UnsplashSearch from "@/components/unsplash/UnsplashSearch.vue";
import UnsplashTag from "@/components/unsplash/UnsplashTag.vue";
import UnsplashCont from "@/components/unsplash/UnsplashCont.vue";
import { ref, onMounted } from "vue";

export default {
  components: {
    ContTitle,
    UnsplashSlider,
    UnsplashSearch,
    UnsplashTag,
    UnsplashCont,
  },

  setup() {
    const unsplash = ref([]);
    const searchs = ref([]);
    const search = ref("marvel");

    const TopUnsplash = async () => {
      await fetch(
        `https://api.unsplash.com/search/photos?client_id=xl3XdD26yx6VUDJS2flUAuj_0xNZpW0a_yfYiBdOX7Y&per_page=30&query=${search.value}`
      )
        .then((response) => response.json())
        .then((result) => {
          // console.log(result);
          unsplash.value = result.results;
          searchs.value = result.results;
        })
        .catch((error) => console.log("error", error));
    };
    onMounted(TopUnsplash);

    return {
      unsplash,
      searchs,
      TopUnsplash,
    };
  },
};
</script>
