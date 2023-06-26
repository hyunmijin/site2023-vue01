<template>
  <div class="youtube__tag">
    <div>
      <button
        v-for="(tag, index) in youtubeTags"
        :key="index"
        @click="btnClick(tag.name)"
      >
        {{ tag.name }}
      </button>
    </div>
  </div>
</template>
<script>
export default {
  props: ["onSearch"],
  data() {
    return {
      youtubeTags: [
        { name: "전체" },
        { name: "미니어처" },
        { name: "다나카 카츠야" },
        { name: "디자인" },
      ],
    };
  },
  methods: {
    btnClick(name) {
      this.onSearch(name);
    },
  },
};
</script>
<style lang="scss" scoped>
.youtube__tag {
  > div {
    justify-content: center;
    display: flex;
    margin-bottom: 50px;
    margin-top: 100px;

    button {
      border: 1px solid #b43e3e;
      padding: 10px 20px;
      margin: 0 10px;
      color: #b43e3e;
      border-radius: 10px;
      cursor: pointer;
    }
  }
}
</style>
