<template>
  <ContTitle title="youtube" />
  <YoutubeSlider />
  <YoutubeSearch />
  <YoutubeTag />
  <YoutubeCont :youtubes="youtube" />
</template>

<script>
import ContTitle from "@/components/layout/ContTitle.vue";
import YoutubeSlider from "@/components/youtube/YoutubeSlider.vue";
import YoutubeSearch from "@/components/youtube/YoutubeSearch.vue";
import YoutubeTag from "@/components/youtube/YoutubeTag.vue";
import YoutubeCont from "@/components/youtube/YoutubeCont.vue";
import { ref } from "vue";

export default {
  components: {
    ContTitle,
    YoutubeSlider,
    YoutubeSearch,
    YoutubeTag,
    YoutubeCont,
  },

  setup() {
    const youtubes = ref([]);

    const TopYoutubes = async () => {
      await fetch(
        "https://api.theyoutubedb.org/3/youtube/popular?api_key=6b6c09dc96064ff256d6877434f62094"
      )
        .then((response) => response.json())
        .then((result) => {
          console.log(result);
          youtubes.value = result.results;
        })
        .catch((error) => console.log("error", error));
    };
    TopYoutubes();

    return {
      youtubes,
      TopYoutubes,
    };
  },
};
</script>
