<template>
  <section class="projects"> 
    <div class="moda_black_bg" v-if="openModal == true">
      <div
        class="modal_white_bg"
        v-for="(cont, index) in ProjectsInfoCont"
        :key="cont"
        v-show="infoIndex == index"
      >
        <p class="modal_close_btn f32" @click="openModal = false">x</p>
        <div class="section_title">
          <h1 class="section_title_txt f32">
            <img src="../../public/img/laptop.png" alt="" />Project
          </h1>
          <p class="modal_sub_title">부산문화관광축제위원회 🎉</p>
        </div>
        <div class="modal_section_cont_wrap">
          <div class="modal_section_top_cont">
            <div class="project_img">
              <div
                class="project_img_bg"
                :style="{ 'background-image': 'url(' + cont.img1 + ')' }"
              ></div>
            </div>
            <ul class="project_introtxt_wrap">
              <li>
                <h2 class="f16">주제:</h2>
                <p class="f16">{{ cont.title }}</p>
              </li>
              <li>
                <h2 class="f16">참여율:</h2>
                <p class="f16">{{ cont.partici }}</p>
              </li>
              <li>
                <h2 class="f16">사용기술:</h2>
                <div class="pro_stacks_wrap">
                  <p class="html_bg f12">{{ cont.html }}</p>
                  <p class="css_bg f12">{{ cont.css }}</p>
                  <p class="java_bg f12">{{ cont.java }}</p>
                  <p class="node_bg f12">{{ cont.node }}</p>
                  <p class="sql_bg f12">{{ cont.sql }}</p>
                </div>
              </li>
              <li>
                <h2 class="f16">작업내용:</h2>
                <p class="f16">
                  {{ cont.content }}
                </p>
              </li>
              <li>
                <h2 class="f16">배포링크:</h2>
                <p class="f16"><a v-bind:href="cont.projectLink">{{ cont.projectLink }}</a></p>
              </li>
              <li>
                <h2 class="f16">깃허브:</h2>
                <p class="f16"><a v-bind:href="cont.projectLink">{{ cont.gitLink }}</a></p>
              </li>
            </ul>
          </div>
          <div class="modal_section_bottom_cont"></div>
        </div>
      </div>
    </div>
    <div class="section_title">
      <h1 class="section_title_txt f32">👉 Projects</h1>
    </div>
    <ul class="projects_cont_wrap">
      <li
        class="projects_cont"
        v-for="(info, index) in ProjectsInfo"
        :key="info"
        @click="modalT(index)"
      >
        <div class="projects_cont_img">
          <img v-bind:src="info.img" alt="" />
        </div>
        <div class="projects_cont_txt">
          <h2 class="f22">{{ info.type }}</h2>
          <p class="f18">{{ info.title }}</p>
        </div>
      </li>
    </ul>
  </section>
</template>
<script>
import { ref } from "vue";
export default {
  setup() {
    let openModal = ref(false);
    let infoIndex = ref(0);
    let ProjectsInfo = [
      {
        type: "개인프로젝트",
        title: "피그말리온",
        img: require("../../public/img/pigmalionfull.png"),
      },
      {
        type: "개인프로젝트",
        title: "서문야시장 리뉴얼",
        img: require("../../public/img/seomoonfull.png"),
      },
      {
        type: "개인프로젝트",
        title: "포트폴리오",
        img: require("../../public/img/portfull.png"),
      },
      {
        type: "팀프로젝트",
        title: "부산문화축제관광 리뉴얼",
        img: require("../../public/img/teamproject.png"),
      },
    ];
    function modalT(index) {
      openModal.value = true;
      infoIndex.value = index;
    }
    let ProjectsInfoCont = [
      {
        title: "피그말리온",
        partici: "100%",
        html: "HTML",
        css: "CSS",
        java: "Javascript",
        node: "Node Js",
        sql: "MySql",
        content:
          "부산문화관광축제위원회 사이트는 위원회에서 진행하는 축제들의 소개를 진행하는 사이트 였다.이 프로젝트에서 중점적으로 구현 하려고 했던 것은 기존 사이트에서 부족했던 디자인,동적, ui ux , 반응형 부분들이였다. 메인페이지를 좀 더 동적으로 디자인하여 축제라는 생동감 있는 컨텐츠들을 사용자들이 체감 할 수 있도록 표현 해줬다. 헤더 부분 또한 ui들이 난잡하여 접근성이 불편 하였는데 헤더의 내용들을 단축 시키고 필요한 서브 페이지들을 묶어 비교적 간단하게 구성 하였다.메인페이지의 전체적인 구성은 디자인적으로 트렌디한 첫섹션, 전체 축제들을 간략하게 소개할 수 있는 두번째 섹션,  가장 가까운 축제의 디데이와 간략한 내용으로 소개하는 세번째 섹션,공지사항과 새소식을 볼 수 있는 네번째 다섯번째 섹션, 주변 관광지를 소개 하는 여섯번째 섹션,패밀리사이트를 한눈에 보기쉽게 구성한 마지막 섹션으로 구성 했다.",
        projectLink: "https://github.com/potato980124",
        gitLink: "https://github.com/potato980124",
        img1: require("../../public/img/teamproject.png"),
        img2: require("../../public/img/teamproject.png"),
      },
      {
        title: "서문야시장 리뉴얼",
        partici: "30%",
        html: "HTML",
        css: "CSS",
        java: "Javascript",
        node: "Node Js",
        sql: "MySql",
        vue: "VUE",
        content:
          "부산문화관광축제위원회 사이트는 위원회에서 진행하는 축제들의 소개를 진행하는 사이트 였다.이 프로젝트에서 중점적으로 구현 하려고 했던 것은 기존 사이트에서 부족했던 디자인,동적, ui ux , 반응형 부분들이였다. 메인페이지를 좀 더 동적으로 디자인하여 축제라는 생동감 있는 컨텐츠들을 사용자들이 체감 할 수 있도록 표현 해줬다. 헤더 부분 또한 ui들이 난잡하여 접근성이 불편 하였는데 헤더의 내용들을 단축 시키고 필요한 서브 페이지들을 묶어 비교적 간단하게 구성 하였다.메인페이지의 전체적인 구성은 디자인적으로 트렌디한 첫섹션, 전체 축제들을 간략하게 소개할 수 있는 두번째 섹션,  가장 가까운 축제의 디데이와 간략한 내용으로 소개하는 세번째 섹션,공지사항과 새소식을 볼 수 있는 네번째 다섯번째 섹션, 주변 관광지를 소개 하는 여섯번째 섹션,패밀리사이트를 한눈에 보기쉽게 구성한 마지막 섹션으로 구성 했다.",
        projectLink: "https://github.com/potato980124",
        gitLink: "https://github.com/potato980124",
        img1: require("../../public/img/teamproject.png"),
        img2: require("../../public/img/teamproject.png"),
      },
      {
        title: "포트폴리오",
        partici: "30%",
        html: "HTML",
        css: "CSS",
        java: "Javascript",
        node: "Node Js",
        sql: "MySql",
        vue: "VUE",
        content:
          "부산문화관광축제위원회 사이트는 위원회에서 진행하는 축제들의 소개를 진행하는 사이트 였다.이 프로젝트에서 중점적으로 구현 하려고 했던 것은 기존 사이트에서 부족했던 디자인,동적, ui ux , 반응형 부분들이였다. 메인페이지를 좀 더 동적으로 디자인하여 축제라는 생동감 있는 컨텐츠들을 사용자들이 체감 할 수 있도록 표현 해줬다. 헤더 부분 또한 ui들이 난잡하여 접근성이 불편 하였는데 헤더의 내용들을 단축 시키고 필요한 서브 페이지들을 묶어 비교적 간단하게 구성 하였다.메인페이지의 전체적인 구성은 디자인적으로 트렌디한 첫섹션, 전체 축제들을 간략하게 소개할 수 있는 두번째 섹션,  가장 가까운 축제의 디데이와 간략한 내용으로 소개하는 세번째 섹션,공지사항과 새소식을 볼 수 있는 네번째 다섯번째 섹션, 주변 관광지를 소개 하는 여섯번째 섹션,패밀리사이트를 한눈에 보기쉽게 구성한 마지막 섹션으로 구성 했다.",
        projectLink: "https://github.com/potato980124",
        gitLink: "https://github.com/potato980124",
        img1: require("../../public/img/teamproject.png"),
        img2: require("../../public/img/teamproject.png"),
      },
      {
        title: "부산문화축제관광 리뉴얼",
        partici: "30%",
        html: "HTML",
        css: "CSS",
        java: "Javascript",
        node: "Node Js",
        sql: "MySql",
        vue: "VUE",
        content:
          "부산문화관광축제위원회 사이트는 위원회에서 진행하는 축제들의 소개를 진행하는 사이트 였다.이 프로젝트에서 중점적으로 구현 하려고 했던 것은 기존 사이트에서 부족했던 디자인,동적, ui ux , 반응형 부분들이였다. 메인페이지를 좀 더 동적으로 디자인하여 축제라는 생동감 있는 컨텐츠들을 사용자들이 체감 할 수 있도록 표현 해줬다. 헤더 부분 또한 ui들이 난잡하여 접근성이 불편 하였는데 헤더의 내용들을 단축 시키고 필요한 서브 페이지들을 묶어 비교적 간단하게 구성 하였다.메인페이지의 전체적인 구성은 디자인적으로 트렌디한 첫섹션, 전체 축제들을 간략하게 소개할 수 있는 두번째 섹션,  가장 가까운 축제의 디데이와 간략한 내용으로 소개하는 세번째 섹션,공지사항과 새소식을 볼 수 있는 네번째 다섯번째 섹션, 주변 관광지를 소개 하는 여섯번째 섹션,패밀리사이트를 한눈에 보기쉽게 구성한 마지막 섹션으로 구성 했다.",
        projectLink: "https://github.com/potato980124",
        gitLink: "https://github.com/potato980124",
        img1: require("../../public/img/teamproject.png"),
        img2: require("../../public/img/teamproject.png"),
      },
    ];
    return {
      ProjectsInfo,
      openModal,
      modalT,
      ProjectsInfoCont,
      infoIndex,
    };
  },
};
</script>
<style scoped>
</style>
