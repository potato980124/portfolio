<template>
  <ul class="about_cont_left_wrap">
    <div class="moda_black_bg" v-if="openModal == true">
      <div class="modal_white_bg">
        <p class="modal_close_btn f32" @click="openModal = false">x</p>
        <div class="section_title">
          <h1 class="section_title_txt f32">Q & A&nbsp;☺</h1>
        </div>
        <div class="modal_section_cont_wrap">
          <h1 class="about_more_tit f20">Q1.자기소개</h1>
            <p class="about_more_txt f20">
              안녕하세요. 개발을 즐기고 개발자로서 성장하고 싶은 프론트엔드
              개발자 홍범진 입니다. <br /><br>
              노원그린컴퓨터아카데미에서 vue.js 활용 프론트엔드 개발자
              양성과정을 수료하였고, <br />
              프론트엔드 과정 이전에는 파이썬 기초과정을 수강 하였습니다.
              <br /><br />
              파이썬 기초과정에서는 코딩에 대한 흥미와 적성을 가늠하는 시간을
              가졌었고,<br />
              프론트엔드 양성과정에서는 개발에 대한 흥미와 적성을 확신하는
              시간을 가졌습니다.<br /><br />
              프론트엔드 양성과정에서 진행했던 개인 프로젝트,팀 프로젝트들을
              진행 하면서 벽에 부딪힐 때 마다<br />
              두려움과 공포심 보다는 즐거움을 느꼈고 벽을 넘었을 때는 엄청난
              행복감이 들었습니다.<br /><br />
              <br />
            </p>
        </div>
      </div>
    </div>
    <li class="profile_img">
      <img src="../../public/img/section1hi.png" alt="" />
    </li>
    <li class="intro_box f14" @click="modalT">더 알아보기🤗</li>
  </ul>
</template>
<script>
import { ref } from "vue";
export default {
  setup() {
    let openModal = ref(false);
    function modalT(index) {
      openModal.value = true;
    }
    return {
      openModal,
      modalT,
    };
  },
};
</script>
<style scoped>
.about_more_tit {
  font-weight: bold;
}
.about_cont_left_wrap {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}
.about_cont_left_wrap .profile_img {
  width: 255px;
}
.about_cont_left_wrap .profile_img > img {
  width: 100%;
}
.about_cont_left_wrap > .intro_box {
  background-color: #333333;
  text-align: center;
  border-radius: 10px;
  height: 37px;
  line-height: 37px;
  color: #fff;
  cursor: pointer;
}
</style>
