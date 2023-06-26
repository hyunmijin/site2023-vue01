<template>
  <div class="youtube__search container">
    <h2 class="blind">검색하기</h2>
    <input
      ref="inputRef"
      @keypress="onKeyPress"
      type="search"
      placeholder="영상을 검색하세요!"
    />
    <button type="submit" @click="onClick" class="button-red">검색하기</button>
  </div>
</template>
<script>
export default {
  mounted() {
    this.$nextTick(() => {
      this.inputRef = this.$refs.inputRef;
    });
  },
  methods: {
    handleSearch() {
      const value = this.inputRef.value;
      this.onSearch(value);
    },
    onKeyPress(event) {
      if (event.key === "Enter") {
        this.handleSearch();
      }
    },
    onClick() {
      this.handleSearch();
    },
  },
  data() {
    return {
      inputRef: null,
    };
  },
  props: {
    onSearch: {
      type: Function,
      required: true,
    },
  },
};
</script>
