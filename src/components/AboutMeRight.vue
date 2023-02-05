<template>
  <div class="about_cont_right_wrap">
    <div class="about_cont_right_tit f12">
      <p>data: {name:”홍범진” , massage: “I Love Develope”}</p>
    </div>
    <div class="about_cont_right_intro f14">
      <p>
        프론트엔드 개발자로서의 성장을 기쁨으로 생각하며, 도전을 즐기며 개발을
        사랑합니다.
      </p>
      <p>
        현재 웹 프론트엔드 개발자 직군의 취업을 희망 하지만, 백엔드도 정복하여
        풀스택 개발자가 되는 것이 목표입니다!
      </p>
    </div>
    <div class="techstacks">
      <div class="techstacks_tit">
        <img src="../../public/img/tech.gif" alt="" />
        <h2 class="f20">Tech Stacks</h2>
        <div class="techtype_box f12">웹 프론트엔드</div>
      </div>
      <div class="techstacks_list">
        <swiper
          :slidesPerView="4"
          :spaceBetween="30"
          :slidesPerGroup="4"
          :loop="true"
          :loopFillGroupWithBlank="true"
          :breakpoints="{
            // set breakpoints here
            1100: {
              slidesPerView: 4,
              spaceBetween: 30,
              slidesPerGroup: 4,
            },
            1024: {
              slidesPerView: 4,
              spaceBetween: 40,
              slidesPerGroup: 4,
            },
            600: {
              slidesPerView: 3,
              spaceBetween: 60,
              slidesPerGroup: 3,
            },
            300: {
              slidesPerView: 2,
              spaceBetween: 60,
              slidesPerGroup: 2,
            },
            0: {
              slidesPerView: 2,
              spaceBetween: 60,
              slidesPerGroup: 2,
            },
          }"
          :navigation="{
            nextEl: '.stacks-button-next',
            prevEl: '.stacks-button-prev',
          }"
          :modules="modules"
          class="mySwiper"
        >
          <div class="stacks-button-next">
            <img src="../../public/img/right-arrow.png" alt="" />
          </div>
          <div class="stacks-button-prev">
            <img src="../../public/img/left-arrow.png" alt="" />
          </div>
          <swiper-slide
            v-for="techstacksdata in techstacks"
            :key="techstacksdata"
          >
            <div class="stack_box" v-if="techstacksdata.stack !== 0">
              <div
                class="stackImg"
                :style="{
                  'background-image': 'url(' + techstacksdata.stackImg + ')',
                }"
              ></div>
              <p class="stackText f16">{{ techstacksdata.stack }}</p>
            </div>
          </swiper-slide>
        </swiper>
      </div>
    </div>
  </div>
</template>
<script>
import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css";
import { Navigation } from "swiper";
import { reactive } from "vue";

export default {
  name: "App",
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    let techstacks = reactive([
      {
        stack: "HTML",
        stackImg: require("../../public/img/html-5.png"),
      },
      {
        stack: "CSS",
        stackImg: require("../../public/img/css-3.png"),
      },
      {
        stack: "JAVASCRIPT",
        stackImg: require("../../public/img/javascript.svg"),
      },
      {
        stack: "VUE.JS",
        stackImg: require("../../public/img/vuelogo.png"),
      },
      {
        stack: "NODE.JS",
        stackImg: require("../../public/img/nodejs.png"),
      },
      {
        stack: "AWS",
        stackImg: require("../../public/img/aws.png"),
      },
      {
        stack: "GITHUB",
        stackImg: require("../../public/img/github.png"),
      },
    ]);
    return {
      modules: [Navigation],
      techstacks,
    };
  },
};
</script>
<style scoped>
.about_cont_right_wrap {
  display: flex;
  flex-direction: column;
}
.about_cont_right_tit {
  margin-bottom: 5px;
}
.about_cont_right_tit > p {
  width: fit-content;
  background-color: #ece8e8;
  color: #007aff;
  padding: 5px 10px;
  box-sizing: border-box;
  border-radius: 10px;
}
.about_cont_right_intro {
  color: #424242;
}
.techstacks {
  margin: 45px 0 0 0;
}
.techstacks_tit {
  display: flex;
  gap: 15px;
  align-items: center;
  margin-bottom: 15px;
}
.techstacks_tit > img {
  width: 24px;
  height: 24px;
}
.techtype_box {
  padding: 5px 10px;
  background-color: #f5f5f5;
  border: 1px solid #dbdbdb;
  border-radius: 10px;
}
.techstacks_list {
  width: 650px;
  background-color: #e7e7e7;
  border: 3px solid #f5f5f5;
  border-radius: 10px;
}
.mySwiper {
  padding: 15px 30px;
  box-sizing: border-box;
}
.stack_box {
  display: flex;
  flex-direction: column;
  gap: 10px;
  align-items: center;
  background: #e7e7e7;
  box-shadow: 0px 8px 32px rgba(110, 110, 110, 0.37);
  border-radius: 10px;
  padding: 17px 30px;
  box-sizing: border-box;
}
.stackImg {
  width: 100%;
  padding-top: 100%;
  background-repeat: no-repeat;
  background-position: center center;
  background-size: contain;
}
.stacks-button-next {
  position: absolute;
  right: 5px;
  top: 50%;
  transform: translateY(-50%);
}
.stacks-button-next > img {
  display: block;
  width: 20px;
}
.stacks-button-prev {
  position: absolute;
  left: 5px;
  top: 50%;
  transform: translateY(-50%);
}
.stacks-button-prev > img {
  display: block;
  width: 20px;
}
.stackText {
  color: #a8a8a8;
}
@media (max-width: 1100px) {
  .about_cont_right_wrap {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  .about_cont_right_intro {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  .techstacks {
    width: 100%;
  }
  .techstacks_list {
    width: 100%;
    background-color: #e7e7e7;
    border: 3px solid #f5f5f5;
    border-radius: 10px;
  }
}
</style>
