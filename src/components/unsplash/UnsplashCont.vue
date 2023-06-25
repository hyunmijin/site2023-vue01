<template>
  <div class="unsplash__cont container">
    <ul>
      <li v-for="(unsplash, index) in unsplash" :key="index">
        <a :href="`https://unsplash.com/photos/${unsplash.id}`" target="_blank">
          <img :src="unsplash.urls.regular" :alt="unsplash.alt_description" />

          <em>
            <span class="title">{{ unsplash.title }}</span>
            <span class="star">{{ unsplash.vote_average }}</span>
          </em>
        </a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    unsplash: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style lang="scss">
.unsplash__cont {
  ul {
    column-count: 4;
    column-gap: 20px;

    li {
      margin-bottom: 20px;
    }
  }
}
</style>
