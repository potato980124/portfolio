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
            안녕하세요. 개발을 즐기고 개발자로서 성장하고 싶은 프론트엔드 개발자
            홍범진 입니다. <br /><br />
            노원그린컴퓨터아카데미에서 vue.js 활용 프론트엔드 개발자 양성과정을
            수료하였고, <br />
            프론트엔드 과정 이전에는 파이썬 기초과정을 수강 하였습니다.
            <br /><br />
            파이썬 기초과정에서는 코딩에 대한 흥미와 적성을 가늠하는 시간을
            가졌었고,<br />
            프론트엔드 양성과정에서는 개발에 대한 흥미와 적성을 확신하는 시간을
            가졌습니다.<br /><br />
            프론트엔드 양성과정에서 진행했던 개인 프로젝트,팀 프로젝트들을 진행
            하면서 벽에 부딪힐 때 마다<br />
            두려움과 공포심 보다는 즐거움을 느꼈고 벽을 넘었을 때는 엄청난
            행복감이 들었습니다.<br /><br />
            <br />
          </p>
          <h1 class="about_more_tit f20">Q2.개발자로 직무를 정한 계기</h1>
          <p class="about_more_txt f20">
            대학 재학중 디지털 마케터 직무로 취업을 준비 하였습니다. <br />
            디지털 마케터 취업을 준비하는 과정에서 개발자와의 원활한
            커뮤니케이션과, <br />
            데이터를 수집할 수 있는 역량을 쌓기 위해 파이썬 기초 과정을 수강
            하였습니다. <br /><br />
            파이썬 기초 과정을 수강 하며 무에서 유를 창조하는 코딩 자체에 흥미가
            생겼고,<br />
            다른 누군가가 만든 제품,프로그램을 마케팅 하는 것이 아니라 스스로
            서비스를 만드는 것에 흥미가 생겼습니다.<br /><br />
            위 경험을 토대로 직접 서비스는 만들어 내는 개발자가 목표가
            되었고,<br />
            첫 발걸음으로 웹 프론트엔드 개발자를 도전하게 되었습니다.
          </p>
          <br /><br /><br />
          <h1 class="about_more_tit f20">Q3.개발자로서 향후 목표</h1>
          <p class="about_more_txt f20">
            먼저,회사에 입사하여 다양한 프론트엔드 실무를 경험하고,업무
            외적으로도 실무에 도움이 될 수 있는 <br />
            프로젝트 설계 및 디자인 패턴을 공부하며,프론트엔드 개발자로서 탄탄한
            실력을 갖출 수 있도록 성장하는 것 입니다. <br /><br />
            이후 목표였던 스스로 서비스를 만드는 개발자가 될 수 있도록 백엔드
            또한 공부를 하여 풀스택 개발자가 되는 것이 목표입니다.
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
  margin-bottom: 20px;
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
@media (max-width: 1100px) {
  .about_cont_left_wrap {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-bottom: 45px;
  }
  .about_cont_left_wrap .profile_img {
    width: 50%;
  }
  .about_cont_left_wrap > .intro_box {
    width: 50%;
    background-color: #333333;
    text-align: center;
    border-radius: 10px;
    height: 37px;
    line-height: 37px;
    color: #fff;
    cursor: pointer;
  }
}
@media(max-width:375px){
  .about_cont_left_wrap .profile_img {
    width: 70%;
  }
  .about_cont_left_wrap > .intro_box {
    width: 70%;
    background-color: #333333;
    text-align: center;
    border-radius: 10px;
    height: 37px;
    line-height: 37px;
    color: #fff;
    cursor: pointer;
  }
}
</style>
