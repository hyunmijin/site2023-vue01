<template>
  <section id="youtubeSection" :class="attr">
    <div class="youtube__inner container">
      <div class="youtube__text">
        <h3>유투버 추천</h3>
        <p>미니어처 유투브</p>
        <a href="/" class="button-red"> 자세히 보기 </a>
      </div>
      <div class="youtube__item">
        <div>
          <img src="@/assets/images/youtube/Rectangle745.png" alt="" />
        </div>
        <div>
          <img src="@/assets/images/youtube/Rectangle745.png" alt="" />
        </div>
        <div>
          <img src="@/assets/images/youtube/Rectangle745.png" alt="" />
        </div>
        <div>
          <img src="@/assets/images/youtube/Rectangle745.png" alt="" />
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
//youtube__section
.youtube__wrap {
  overflow: hidden;
}
.youtube__inner {
  height: 600px;
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
.youtube__item {
  display: flex;
  // width: 100%;
  position: absolute;
  > div {
    margin-right: 20px;
    width: 400px;
    // background-color: #ccc;
    iframe {
      width: 100%;
      border-radius: 5%;
      height: 220px;
    }
  }
}

// youtube__page
.youtube__slider {
  display: none;
}
.youtube__search {
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
      }
    }
  }
}
.youtube__cont {
  ul {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    margin-bottom: 100px;

    li {
      width: 31.333%;
      margin-bottom: 4%;

      img {
        width: 400px;
        height: 200px;
        object-fit: cover;
        border-radius: 5px;
      }

      span {
        display: block;
        margin: 4px 0;
        margin-top: 10px;
        font-weight: bold;

        overflow: hidden;
        white-space: nowrap;
        text-overflow: ellipsis;
        -webkit-line-clamp: 1; /* 라인수 */
        -webkit-box-orient: vertical;
        word-wrap: break-word;
      }
    }
  }
}
</style>
