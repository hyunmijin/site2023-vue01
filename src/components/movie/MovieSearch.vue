<template>
  <div className="movie__search">
    <input type="text" placeholder="영화 검색하기" />
    <button>검색</button>
  </div>
</template>

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
