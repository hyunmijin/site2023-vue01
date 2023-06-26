<template>
  <div class="movie__search container">
    <h2 class="blind">검색하기</h2>
    <input
      ref="inputRef"
      type="search"
      @keypress="onKeyPress"
      placeholder="영화를 검색하세요 !"
    />
    <button type="submit" @click="onClick">검색하기</button>
  </div>
</template>

<script>
export default {
  methods: {
    onKeyPress(event) {
      if (event.key === "Enter") {
        this.handleSearch();
      }
    },
    onClick() {
      this.handleSearch();
    },
    handleSearch() {
      const value = this.$refs.inputRef.value;
      this.$emit("search", value);
    },
  },
};
</script>

<style lang="scss">
.movie__search {
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
