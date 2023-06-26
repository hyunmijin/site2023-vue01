<template>
  <div class="movie__tag container">
    <ul>
      <li>
        <router-link to="" @click="onClick('10749')">로맨스영화</router-link>
      </li>
      <li>
        <router-link to="" @click="onClick('28')">액션영화</router-link>
      </li>
      <li>
        <router-link to="" @click="onClick('35')">코미디영화</router-link>
      </li>
      <li>
        <router-link to="" @click="onClick('16')">애니메이션</router-link>
      </li>
      <li>
        <router-link to="" @click="onClick('27')">공포영화</router-link>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  methods: {
    onClick(value) {
      this.$emit("search", value);
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
          transition: all 0.5s;
        }
      }
    }
  }
}
</style>
