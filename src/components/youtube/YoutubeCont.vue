<template>
  <div class="youtube__cont container">
    <ul>
      <li v-for="(youtube, index) in youtubes" :key="index">
        <img
          :src="youtube.snippet.thumbnails.medium.url"
          :alt="youtube.snippet.title"
        />
        <span>{{ youtube.snippet.title }}</span>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    youtubes: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style lang="scss">
.youtube__cont {
  ul {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;

    li {
      width: 32.333%;
      position: relative;
      margin-bottom: 2%;

      .title {
        font-size: 20px;
        padding: 3px 0;
        display: inline-block;

        &:hover {
          text-decoration: underline;
          text-underline-position: under;
        }
      }
      .star {
        position: absolute;
        right: 20px;
        top: 20px;
        width: 30px;
        height: 30px;
        background-color: #fff;
        text-align: center;
        line-height: 30px;
        border-radius: 50%;
        font-size: 12px;
      }
    }
  }
}
</style>
