<template>
  <div class="unsplash__tag container">
    <ul>
      <li>
        <router-link to="" @click="onClick('miniature')">미니어처</router-link>
      </li>
      <li>
        <router-link to="" @click="onClick('morden')">전시회</router-link>
      </li>
      <li>
        <router-link to="" @click="onClick('sculpture')">미술작품</router-link>
      </li>
      <li>
        <router-link to="" @click="onClick('design')">디자인</router-link>
      </li>
      <li>
        <router-link to="" @click="onClick('illustration')"
          >일러스트</router-link
        >
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
<style lang="scss" scoped>
.unsplash__tag {
  ul {
    justify-content: center;
    display: flex;
    margin-bottom: 50px;
    margin-top: 100px;

    li {
      border: 1px solid #b43e3e;
      padding: 10px 20px;
      margin: 0 10px;
      color: #b43e3e;
      border-radius: 10px;
    }
  }
}
</style>
