<template>
  <section id="unsplashSection" :class="attr">
    <div class="unsplash__inner container">
      <div class="unsplash__text">
        <h3>이미지 추천</h3>
        <p>서울 전시 작품</p>
        <a href="/" class="button-blue"> 자세히 보기 </a>
      </div>
      <div class="unsplash__item">
        <div>
          <img src="@/assets/images/unsplash/01.jpg" alt="" />
        </div>
        <div>
          <img src="@/assets/images/unsplash/02.jpg" alt="" />
        </div>
        <div>
          <img src="@/assets/images/unsplash/3.jpg" alt="" />
        </div>
        <div>
          <img src="@/assets/images/unsplash/04.jpg" alt="" />
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
//unsplash__wrap
.unsplash__wrap {
  overflow: hidden;
}
.unsplash__inner {
  height: 600px;
  // background-color: #ccc;

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
.unsplash__item {
  display: flex;
  // width: 100%;
  position: absolute;
  > div {
    margin-right: 20px;
    width: 400px;
    // background-color: #ccc;

    img {
      width: 100%;
      border-radius: 5%;
      height: 220px;
      object-fit: cover;
    }
  }
}
</style>
