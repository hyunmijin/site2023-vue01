<template>
  <ContTitle title="youtube" />
  <YoutubeSlider />
  <YoutubeSearch />
  <YoutubeTag />
  <YoutubeCont :youtubes="searchs" />
</template>

<script>
import ContTitle from "@/components/layout/ContTitle.vue";
import YoutubeSlider from "@/components/youtube/YoutubeSlider.vue";
import YoutubeSearch from "@/components/youtube/YoutubeSearch.vue";
import YoutubeTag from "@/components/youtube/YoutubeTag.vue";
import YoutubeCont from "@/components/youtube/YoutubeCont.vue";
import { ref, onMounted } from "vue";

export default {
  props: {
    youtubes: {
      type: Array,
      required: true,
    },
  },

  components: {
    ContTitle,
    YoutubeSlider,
    YoutubeSearch,
    YoutubeTag,
    YoutubeCont,
  },

  setup() {
    const search = ref("marvel");
    const searchs = ref([]);

    const TopYoutubes = async () => {
      await fetch(
        `https://youtube.googleapis.com/youtube/v3/search?part=snippet&maxResults=30&q=${search.value}&key=AIzaSyChAblDVV_gbDjwCCNxAKcECZvTBLtjcQ8`
      )
        .then((response) => response.json())
        .then((result) => {
          console.log(result);
          searchs.value = result.items;
        })
        .catch((error) => console.log("error", error));
    };

    onMounted(TopYoutubes);

    return {
      search,
      searchs,
    };
  },
};
</script>
