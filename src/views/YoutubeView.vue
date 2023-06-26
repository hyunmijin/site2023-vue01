<template>
  <ContTitle title="youtube" />
  <YoutubeSlider :youtubes="youtubes" />
  <YoutubeSearch @search="SearchYoutube" />
  <YoutubeTag @search="SearchYoutube" />
  <YoutubeCont :youtubes="youtubes" />
</template>

<script>
import ContTitle from "@/components/layout/ContTitle.vue";
import YoutubeSearch from "@/components/youtube/YoutubeSearch.vue";
import YoutubeTag from "@/components/youtube/YoutubeTag.vue";
import YoutubeCont from "@/components/youtube/YoutubeCont.vue";
import { ref } from "vue";

export default {
  components: {
    ContTitle,
    YoutubeSearch,
    YoutubeTag,
    YoutubeCont,
  },

  setup() {
    const youtubes = ref([]);

    const TopYoutubes = async () => {
      await fetch(
        `https://youtube.googleapis.com/youtube/v3/search?part=snippet&maxResults=30&q=mordern%20art&type=video&key=AIzaSyChAblDVV_gbDjwCCNxAKcECZvTBLtjcQ8`
      )
        .then((response) => response.json())
        .then((result) => {
          console.log(result.items);
          youtubes.value = result.items;
        })
        .catch((error) => console.log(error));
    };
    TopYoutubes();

    const SearchYoutube = async (query) => {
      await fetch(
        `https://youtube.googleapis.com/youtube/v3/search?part=snippet&maxResults=28&q=${query}&type=video&key=AIzaSyAK7YibL0SlW8R3bLjAuG8S33Ps3XRRAio`
      )
        .then((response) => response.json())
        .then((result) => {
          youtubes.value = result.items;
        })
        .catch((error) => console.log("error", error));
    };
    return {
      TopYoutubes,
      youtubes,
      SearchYoutube,
    };
  },
};
</script>
