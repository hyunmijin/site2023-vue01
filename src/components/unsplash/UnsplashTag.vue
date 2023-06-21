<template>
  <div className="unsplash__tag">
    <ul>
      <li><a href="/">전체</a></li>
      <li><a href="/">다나카 타츠야 작품</a></li>
      <li><a href="/">작품사진</a></li>
      <li><a href="/">인기사진</a></li>
      <li><a href="/">최근사진</a></li>
    </ul>
  </div>
</template>

<style lang="scss" scoped>
.unsplash__tag {
  ul {
    justify-content: center;
    display: flex;
    margin-bottom: 50px;
    margin-top: 100px;

    li {
      a {
        border: 1px solid #b43e3e;
        padding: 10px 20px;
        margin: 0 10px;
        color: #b43e3e;
        border-radius: 10px;
      }
    }
  }
}
</style>
