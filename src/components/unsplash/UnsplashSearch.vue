<template>
  <div class="unsplash__search">
    <input
      type="text"
      placeholder="이미지 검색하기"
      v-model="inputValue"
      @keypress.enter="handleSearch"
    />

    <button @click="handleSearch">검색</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      inputValue: "",
    };
  },
  methods: {
    handleSearch() {
      this.$emit("search", this.searchTerm);
    },
  },
};
</script>

<style lang="scss">
.unsplash__search {
  text-align: center;
  margin-bottom: 50px;

  input {
    border: 1px solid #e8ecf2;
    font-size: 16px;
    padding: 10px 20px;
    @include border(50px);
    min-width: 500px;
    margin-right: 10px;
  }
  button {
    @include button(#b43e3e, #ffffff);
    @include border(50px);
  }
}
</style>
