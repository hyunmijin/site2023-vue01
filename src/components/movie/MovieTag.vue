<template>
  <div class="movie__tag">
    <div>
      <ul>
        <li
          v-for="(tag, index) in movieTagList"
          :key="index"
          :class="{ active: tag.name === activeTag }"
          @click="btnClick(tag.name)"
        >
          <a href="#">{{ tag.name }}</a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      movieTagList: [
        {
          name: "인기 영화",
          url: "https://api.themoviedb.org/3/movie/popular",
        },
        {
          name: "현재 상영작",
          url: "https://api.themoviedb.org/3/movie/now_playing",
        },
        {
          name: "최신 영화",
          url: "https://api.themoviedb.org/3/movie/upcoming",
        },
        {
          name: "인기 티비쇼",
          url: "https://api.themoviedb.org/3/tv/popular",
        },
        {
          name: "티비쇼 순위",
          url: "https://api.themoviedb.org/3/tv/top_rated",
        },
      ],
      activeTag: "인기 영화",
    };
  },
  methods: {
    btnClick(tagName) {
      const clickedTag = this.movieTagList.find((tag) => tag.name === tagName);
      console.log(clickedTag.url);
      if (clickedTag) {
        this.activeTag = clickedTag.name;
        this.onSearch(clickedTag.url);
      }
    },
  },
  props: {
    onSearch: {
      type: Function,
      required: true,
    },
  },
};
</script>

<style lang="scss">
.movie__tag {
  ul {
    display: flex;
    justify-content: center;
    margin-top: 100px;
    margin-bottom: 50px;

    li {
      a {
        display: inline-block;
        border: 1px solid #b43e3e;
        padding: 10px 20px;
        margin: 0 10px;
        color: #b43e3e;
        cursor: pointer;

        &:hover {
          background-color: #b43e3e;
          color: #fff;
        }
      }
    }
    li.active a {
      background-color: #b43e3e;
      color: #fff;
    }
  }
}
</style>
