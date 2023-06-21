<template>
  <section id="movieSection" :class="attr">
    <div class="movie__inner container">
      <div class="move__text">
        <h3>영화 추천</h3>
        <p>러빙 빈센트, 호크니, 뱅크시, 진주 귀걸이를 한 소녀</p>
        <a href="/" class="button-red"> 자세히 보기 </a>
      </div>
      <div class="movie__item">
        <div>
          <img src="@/assets/images/movie/01.jpg" alt="" />
        </div>
        <div>
          <img src="@/assets/images/movie/02.jpg" alt="" />
        </div>
        <div>
          <img src="@/assets/images/movie/03.jpg" alt="" />
        </div>
        <div>
          <img src="@/assets/images/movie/04.jpg" alt="" />
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  props: {
    attr: String,
  },
};
</script>

<style lang="scss">
//movie__wrap
.movie__wrap {
  overflow: hidden;
}
.movie__inner {
  height: 750px;
  h3 {
    font-size: 50px;
    margin-bottom: 20px;
  }
  p {
    font-size: 24px;
    margin-bottom: 20px;
  }
  a {
    border-radius: 50px;
    margin-bottom: 100px;
  }
}
.movie__item {
  display: flex;
  // width: 100%;
  position: absolute;
  > div {
    margin-right: 20px;
    width: 400px;
    // background-color: #ccc;

    img {
      width: 80%;
      border-radius: 5%;
      height: 500px;
      object-fit: cover;
    }
  }
}
</style>
