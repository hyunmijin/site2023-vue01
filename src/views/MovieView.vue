<template>
  <ContTitle title="movies" />
  <MovieSlider :movies="movies" />
  <MovieSearch @search="SearchMovie" />
  <MovieTag @search="SearchByGenre" />
  <MovieCont :movies="movies" />
</template>

<script>
import ContTitle from "@/components/layout/ContTitle.vue";
import MovieSlider from "@/components/movie/MovieSlider.vue";
import MovieSearch from "@/components/movie/MovieSearch.vue";
import MovieTag from "@/components/movie/MovieTag.vue";
import MovieCont from "@/components/movie/MovieCont.vue";
import { ref } from "vue";

export default {
  components: {
    ContTitle,
    MovieSlider,
    MovieSearch,
    MovieTag,
    MovieCont,
  },

  setup() {
    const movies = ref([]);

    const TopMovies = async () => {
      await fetch(
        `https://api.themoviedb.org/3/movie/popular?api_key=6b6c09dc96064ff256d6877434f62094&language=ko-KR&query=SEARCH_QUERY&page=1&include_adult=false&limit=30`
      )
        .then((response) => response.json())
        .then((result) => {
          console.log(result.results);
          movies.value = result.results;
        }) // 첫 번째로 확인해야할 것(console로 result값 불러오는지)
        .catch((error) => console.error("error", error));
    };
    TopMovies();

    const SearchMovie = async (query) => {
      await fetch(
        `https://api.themoviedb.org/3/search/movie?api_key=86951144e4cb4c72a22189f65fc8c04b&language=ko-KR&query=SEARCH_QUERY&page=1&include_adult=false&limit=30&query=${query}`
      )
        .then((response) => response.json())
        .then((result) => {
          movies.value = result.results;
        })
        .catch((error) => console.log(error));
    };

    const SearchByGenre = async (genreId) => {
      await fetch(
        `https://api.themoviedb.org/3/discover/movie?api_key=6b6c09dc96064ff256d6877434f62094&language=ko-kr&with_genres=${genreId}`
      )
        .then((response) => response.json())
        .then((result) => {
          movies.value = result.results;
        })
        .catch((err) => console.error(err));
    };
    return {
      movies,
      TopMovies,
      SearchMovie,
      SearchByGenre,
    };
  },
};
</script>
