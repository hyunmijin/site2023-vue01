<template>
  <section id="introSection" :class="attr">
    <h3 class="blind">프론트앤드 커리큘럼 과정 소개</h3>
    <div class="intro__inner container">
      <div class="intro__title">
        <span>MINIATURE</span>
        <h2 v-html="title"></h2>
        <p v-html="desc"></p>
      </div>
      <div class="intro__desc">
        <div v-for="(text, index) in texts" :key="index">
          <h4 :class="'icon-bg' + (index + 1)">{{ text.title }}</h4>
          <p>
            {{ text.desc }}
          </p>
        </div>
        <!-- <div class="icon-bg1">
          <h4>아이디어</h4>
          <p>
            우리가 일상적으로 사용하는 물건들을 가지고 디오라마 스타일의 사진을
            한컷 한컷 담아 냅니다.
          </p>
        </div>
        <div class="icon-bg2">
          <h4>캘린더</h4>
          <p>
            타나카 타츠야는 2011년 4월부터 현재까지 하루도 빠짐없이 'MINIATURE
            CALENDAR'를 통해 작품을 발표하고 있다.
          </p>
        </div>
        <div class="icon-bg3">
          <h4>기록</h4>
          <p>
            그의 작품은 단순히 작고 섬세한 미니어처를 넘어서서 ‘스토리텔링’이
            가미된 작품으로 거듭난다.
          </p>
        </div>
        <div class="icon-bg4">
          <h4>미니어처</h4>
          <p>소유하고 있는 미니어처들이 수없이 많단고 한다.</p>
        </div> -->
      </div>
    </div>
  </section>
</template>

<script>
export default {
  props: {
    attr: String,
  },
  data: function () {
    return {
      title: "10년째 매일매일!<br />미니어처 사진가",
      desc: "우리가 일상적으로 사용하는 물건들을 가지고 디오라마 스타일의 사진을 한컷 한컷 담아 냅니다.",
      texts: [
        {
          title: "아이디어",
          desc: "우리가 일상적으로 사용하는 물건들을 가지고 디오라마 스타일의 사진을 한컷 한컷 담아 냅니다.",
        },
        {
          title: "캘린더",
          desc: "타나카 타츠야는 2011년 4월부터 현재까지 하루도 빠짐없이 'MINIATURE CALENDAR'를 통해 작품을 발표하고 있다.",
        },
        {
          title: "기록",
          desc: "그의 작품은 단순히 작고 섬세한 미니어처를 넘어서서 ‘스토리텔링’이가미된 작품으로 거듭난다.",
        },
        {
          title: "미니어처",
          desc: "소유하고 있는 미니어처들이 수없이 많단고 한다.",
        },
      ],
    };
  },
};
</script>

<style lang="scss">
//  intro
.intro__wrap {
}
.intro__inner {
  display: flex;
  justify-content: space-between;
}
.intro__title {
  width: 33%;
  span {
    background-color: #ff3344;
    font-size: 14px;
    padding: 4px 30px 2px;
    color: #fff;
    border-radius: 40px;
    text-transform: uppercase;
    margin-bottom: 10px;
    display: inline-block;
  }
  h2 {
    font-size: 50px;
    font-weight: 700;
    line-height: 1.2;
    margin-bottom: 30px;
  }
  p {
    font-size: 18px;
    line-height: 1.5;
    font-weight: 500;
  }
}
.intro__desc {
  width: 66%;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  > div {
    width: 48%;
    margin-bottom: 40px;
    h4 {
      font-weight: 800;
      font-size: 24px;
      margin-bottom: 15px;
    }
    &:nth-child(3) {
      margin-bottom: 0;
    }
    &:nth-child(4) {
      margin-bottom: 0;
    }
  }
}
</style>
