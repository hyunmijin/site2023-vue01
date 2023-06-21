<template>
  <div className="youtube__tag">
    <ul>
      <li><a href="/">전체</a></li>
      <li><a href="/">음악영화</a></li>
      <li><a href="/">미술영화</a></li>
      <li><a href="/">고전영화</a></li>
      <li><a href="/">최신영화</a></li>
    </ul>
  </div>
</template>

<style lang="scss" scoped>
.youtube__tag {
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
