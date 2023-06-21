<template>
  <section id="sliderSection" :class="attr">
    <div class="slider__inner">
      <h2 class="blind">배너 슬라이드</h2>
      <swiper
        :modules="modules"
        :slides-per-view="1"
        :space-between="50"
        navigation
        :pagination="{ clickable: true }"
        :autoplay="{
          delay: 2500,
          disableOnInteraction: false,
        }"
        @swiper="onSwiper"
        @slideChange="onSlideChange"
      >
        <swiper-slide v-for="(slider, index) in sliders" :key="index">
          <div class="slider__img">
            <div class="slider s1 container">
              <div class="text">
                <h3 v-html="slider.title"></h3>
                <p>{{ slider.desc }}</p>
                <a href="#" class="more button-blue">더 알아보기</a>
              </div>
              <div class="img" aria-label="hidden">
                <img :src="slider.iconimage1" :alt="slider.title" />
                <img :src="slider.iconimage2" :alt="slider.title" />
                <img :src="slider.iconimage3" :alt="slider.title" />
              </div>
              <div class="circle" aria-label="hidden">
                <span class="circle c1"></span>
                <span class="circle c2"></span>
                <span class="circle c3"></span>
                <span class="circle c4"></span>
                <span class="circle c5"></span>
              </div>
            </div>
          </div>
        </swiper-slide>
      </swiper>
      <!-- <div class="slider__btn">
        <a href="#" class="left"><span class="ir">이전 이미지</span></a>
        <a href="#" class="right"><span class="ir">다음 이미지</span></a>
      </div>
      <div class="slider__dot">
        <a href="#" class="dot active"><span class="ir">1번 이미지</span></a>
        <a href="#" class="dot"><span class="ir">2번 이미지</span></a>
        <a href="#" class="dot"><span class="ir">3번 이미지</span></a>
      </div> -->
    </div>
  </section>
</template>

<script>
import {
  Navigation,
  Pagination,
  Scrollbar,
  EffectFade,
  Autoplay,
  Parallax,
} from "swiper";

import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css/navigation";
import "swiper/css/pagination";
import "swiper/css/scrollbar";

import "swiper/css";

export default {
  props: {
    attr: String,
  },

  data: function () {
    return {
      sliders: [
        {
          title: "Tanaka <br />Tatsuya",
          desc: "유쾌한 상상을 통해 일상을 즐겁게 만드는 미니어처 사진가",
          iconimage1: "./assets/images/slider/bell.png",
          iconimage2: "./assets/images/slider/calendar.png",
          iconimage3: "./assets/images/slider/clapperboard.png",
        },
        {
          title: "Tanaka <br />Tatsuya",
          desc: "유쾌한 상상을 통해 일상을 즐겁게 만드는 미니어처 사진가",
          iconimage1: "./assets/images/slider/bell.png",
          iconimage2: "./assets/images/slider/calendar.png",
          iconimage3: "./assets/images/slider/clapperboard.png",
        },
        {
          title: "Tanaka <br />Tatsuya",
          desc: "유쾌한 상상을 통해 일상을 즐겁게 만드는 미니어처 사진가",
          iconimage1: "./assets/images/slider/bell.png",
          iconimage2: "./assets/images/slider/calendar.png",
          iconimage3: "./assets/images/slider/clapperboard.png",
        },
      ],
    };
  },
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    const onSwiper = (swiper) => {
      console.log(swiper);
    };
    const onSlideChange = () => {
      console.log("slide change");
    };
    return {
      onSwiper,
      onSlideChange,
      modules: [
        Navigation,
        Pagination,
        Scrollbar,
        EffectFade,
        Autoplay,
        Parallax,
      ],
    };
  },
};
</script>

<style lang="scss">
//slider__wrap
.slider__inner {
  position: relative;
  .slider__img {
    .slider {
      .text {
        h3 {
          font-size: 110px;
          font-weight: 800;
          text-transform: uppercase;
          line-height: 1;
          margin-bottom: 40px;
          margin-top: 50px;
          padding-top: 100px;
        }
        p {
          font-size: 24px;
          line-height: 1.3;
          margin-bottom: 180px;
        }
        .more {
          font-size: 18px;
          position: absolute;
          width: 190px;
          height: 45px;
          left: 0;
          bottom: -80px;
        }
      }
      .img {
        width: 600px;
        height: 600px;
        // background: #fff;
        background-image: url(@/assets/images/slider/header_gradient.png);
        // background-image: url(../assets/images/header_gradient.png);
        background-size: cover;
        position: absolute;
        right: 0;
        top: -40px;

        img {
          &:nth-child(1) {
            position: absolute;
            width: 300px;
          }
          &:nth-child(2) {
            position: absolute;
            width: 300px;
            right: 0;
            bottom: 140px;
          }
          &:nth-child(3) {
            position: absolute;
            width: 300px;
            bottom: 10px;
            left: 30px;
          }
        }
      }
      .circle {
        span {
          display: block;
          position: absolute;
          left: 50%;
          top: 50%;
          width: 20px;
          height: 20px;
          border-radius: 50%;
        }
        span:nth-child(1) {
          background-color: var(--button_blue);
          left: 50%;
          width: 10px;
          height: 10px;
        }
        span:nth-child(2) {
          background-color: var(--button_red);
          top: 20%;
          left: -10%;
          width: 40px;
          height: 40px;
        }
        span:nth-child(3) {
          background-color: var(--button_green);
          left: 100%;
          top: 10%;
        }
        span:nth-child(4) {
          background-color: var(--button_red);
          left: 17%;
          top: -10%;
          width: 10px;
          height: 10px;
        }
        span:nth-child(5) {
          background-color: var(--button_blue);
          left: 90%;
          top: 80%;
          width: 30px;
          height: 30px;
        }
      }
    }
  }

  .slider__btn {
    > a {
      position: absolute;
      top: 50%;
      transform: translateY(-50%);
      width: 22px;
      height: 40px;
      transition: opacity 0.3s;

      &:hover {
        opacity: 0.5;
      }
    }
    .left {
      left: 20px;
      background-image: url(@/assets/images/slider/sliderleft.png);
    }
    .right {
      right: 20px;
      background-image: url(@/assets/images/slider/sliderright.png);
    }
  }
  .slider__dot {
    position: absolute;
    left: 50%;
    bottom: -40%;
    transform: translateX(-50%);
    a {
      display: inline-block;
      width: 16px;
      height: 16px;
      border-radius: 50%;
      margin: 0 5px;
      border: 4px solid #ff3344;
      background-color: #ff3344;
      box-shadow: 0 0 0 3px transparent;
      &.active {
        box-shadow: 0 0 0 3px #ff3344;
        border-width: 4px;
        background-color: #fff;
      }
    }
  }
}
</style>
