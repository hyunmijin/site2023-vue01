<template>
  <section id="portSection" :class="attr">
    <h3>MINIATURE CALENDAR</h3>
    <div class="port__inner container center">
      <div class="port__btn"></div>
      <div class="port__cont">
        <div>
          <div class="port" v-for="(text, index) in texts" :key="index">
            <figure class="port__header">
              <img :src="text.img" alt="text.title" />
            </figure>
            <div class="port__body">
              <div>
                <h4>{{ text.title }}</h4>
                <p>{{ text.desc }}</p>
              </div>
            </div>
          </div>
          <!-- <div class="port">
            <figure class="port__header">
              <img src="@/assets/images/port/230512fri.jpg" alt="" />
            </figure>
            <div class="port__body">
              <div>
                <h4>Brush of the Wild</h4>
                <p>-230512fri</p>
              </div>
            </div>
          </div>
          <div class="port">
            <figure class="port__header">
              <img src="@/assets/images/port/230522mon1.jpg" alt="" />
            </figure>
            <div class="port__body">
              <div>
                <h4>Breathing</h4>
                <p>-230522mon1</p>
              </div>
            </div>
          </div> -->
        </div>
        <div>
          <div class="port" v-for="(text, index) in texts1" :key="index">
            <figure class="port__header">
              <img :src="text.img" alt="text.title" />
            </figure>
            <div class="port__body">
              <div>
                <h4>{{ text.title }}</h4>
                <p>{{ text.desc }}</p>
              </div>
            </div>
          </div>
          <!-- <div class="port">
            <figure class="port__header">
              <img src="@/assets/images/port/230414fri1.jpg" alt="" />
            </figure>
            <div class="port__body">
              <div>
                <h4>Fuku1 Grand Prix</h4>
                <p>-230414fri1</p>
              </div>
            </div>
          </div>
          <div class="port">
            <figure class="port__header">
              <img src="@/assets/images/port/230421fri1.jpg" alt="" />
            </figure>
            <div class="port__body">
              <div>
                <h4>Sweet Mario Bros</h4>
                <p>-230421fri1</p>
              </div>
            </div>
          </div>
          <div class="port">
            <figure class="port__header">
              <img src="@/assets/images/port/230307tue.jpg" alt="" />
            </figure>
            <div class="port__body">
              <div>
                <h4>Barrel Sauna</h4>
                <p>-230307tue</p>
              </div>
            </div>
          </div> -->
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
  data: function () {
    return {
      texts: [
        {
          img: "./assets/images/port/230511thu.jpg",
          title: "아이디어",
          desc: "-230511thu",
        },
        {
          img: "./assets/images/port/230512fri.jpg",
          title: "Brush of the Wild",
          desc: "-230512fri",
        },
        {
          img: "./assets/images/port/230522mon1.jpg",
          title: "Breathing",
          desc: "-230522mon1",
        },
        // {
        //   img: "./assets/images/port/230414fri1.jpg",
        //   title: "Fuku1 Grand Prix",
        //   desc: "-230414fri1",
        // },
        // {
        //   img: "./assets/images/port/230421fri1.jpg.jpg",
        //   title: "Sweet Mario Bros",
        //   desc: "-230421fri1",
        // },
        // {
        //   img: "./assets/images/port/230307tue.jpg",
        //   title: "Barrel Sauna",
        //   desc: "-230307tue",
        // },
      ],
      texts1: [
        {
          img: "./assets/images/port/230414fri1.jpg",
          title: "Fuku1 Grand Prix",
          desc: "-230414fri1",
        },
        {
          img: "./assets/images/port/230421fri1.jpg",
          title: "Sweet Mario Bros",
          desc: "-230421fri1",
        },
        {
          img: "./assets/images/port/230307tue.jpg",
          title: "Barrel Sauna",
          desc: "-230307tue",
        },
      ],
    };
  },
};
</script>

<style lang="scss">
// port__wrap
.port__wrap {
  overflow: hidden;
  h3 {
    font-weight: 800;
    margin-bottom: 50px;
  }
}
.port__inner {
  margin-top: 50px;
}
.port__cont {
  > div {
    // background-color: #ccc;
    margin-bottom: 30px;
    display: flex;
    justify-content: space-between;
  }

  .port {
    // width: 100%;
    .port__header {
      // background-color: #000;

      img {
        width: 400px;
        border-radius: 5%;
        // background-color: #ccc;
      }
    }

    .port__body {
      margin-top: 15px;
      display: flex;

      > div {
        line-height: 1.5;
        margin-left: 10px;
        text-align: start;
      }
      img {
        width: 43px;
        height: 43px;
      }
      h4 {
        font-size: 20px;
        font-weight: 900;
      }
      p {
        font-weight: 100;
      }
    }
  }
}
</style>
