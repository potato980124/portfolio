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
                  <p class="html_bg f12" v-if="cont.html !== false">{{ cont.html }}</p>
                  <p class="css_bg f12" v-if="cont.css !== false">{{ cont.css }}</p>
                  <p class="java_bg f12" v-if="cont.java !== false">{{ cont.java }}</p>
                  <p class="node_bg f12" v-if="cont.node !== false">{{ cont.node }}</p>
                  <p class="sql_bg f12" v-if="cont.sql !== false">{{ cont.sql }}</p>
                  <p class="sql_bg f12" v-if="cont.vue !== false">{{ cont.vue }}</p>
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
                <p class="f16"><a v-bind:href="cont.gitLink">{{ cont.gitLink }}</a></p>
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
        img: require("../../public/img/portopolio.png"),
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
        vue: false,
        content:
          "바닐라 자바스크립트와 node를 이용하여 로그인과 회원가입을 구현했습니다. 칼로리캘린더에서 식품영양 api를 활용하여 오늘 먹은 음식들의 영양 정보와 칼로리들을 합산하여 보여주고 회원가입 때 기재한 목표 몸무게와 칼로리캘린더에서 기재한 현재 몸무게를 기반하여 목표 달성률 또한 사용자에게 제공하는 다이어트 웹 사이트입니다. 추후 커뮤니티 기능과 음식 검색 기능을 추가할 예정입니다.",
        projectLink: "http://pigmalionnew-env.eba-75qpnq5q.ap-northeast-1.elasticbeanstalk.com/",
        gitLink: "https://github.com/potato980124/pigmalion",
        img1: require("../../public/img/pigmalionfull.png")
      },
      {
        title: "서문야시장 리뉴얼",
        partici: "100%",
        html: "HTML",
        css: "CSS",
        java: "Javascript",
        node: "Node Js",
        sql: "MySql",
        vue: false,
        content:
          "기존 서문야시장 웹사이트를 리뉴얼한 웹사이트입니다. 시장의 특성상 연령층이 높은 사용자들을 고려해 최대한 단순하고 직관적인 UI/UX 및 색감을 선정하여 리뉴얼 하였습니다. 로그인, 회원가입, 공지사항, 현장스케치(갤러리), 야시장안내,매대위치, 오시는 길 기능 등을 사용 할 수 있습니다. 공지사항 및 갤러리는 공지등록, 삭제, 수정이 가능하고 매대위치에서 또한 동일한 기능과 매대 검색을 통해 원하는 매대를 쉽게 찾을 수 있도록 하였습니다. 매대위치와 오시는 길에서 카카오맵 api를 활용 하였습니다.",
        projectLink: "http://firstseomoon-env.eba-dcdt2xqa.ap-northeast-1.elasticbeanstalk.com",
        gitLink: "https://github.com/potato980124/seomoon",
        img1: require("../../public/img/seomoonfull.png"),
      },
      {
        title: "포트폴리오",
        partici: "100%",
        html: "HTML",
        css: "CSS",
        java: false,
        node: false,
        sql: false,
        vue: "VUE",
        content:
          "VUE를 활용하여 제작한 포트폴리오 웹사이트입니다. VUE.Js를 활용해 개발하였으며 VUE에 대한 이해와 역량을 쌓을 수 있었습니다. 별다른 데이터가 없었기 때문에 비교적 간단한 Firebase를 사용하여 배포하였습니다.",
        projectLink: "",
        gitLink: "https://github.com/potato980124/portfolio",
        img1: require("../../public/img/portopolio.png")
      },
      {
        title: "부산문화축제관광 리뉴얼",
        partici: "50%",
        html: "HTML",
        css: "CSS",
        java: "Javascript",
        node: "Node Js",
        sql: "MySql",
        vue: false,
        content:
          "부산문화관광축제위원회 사이트는 위원회에서 진행하는 축제들의 소개를 진행하는 사이트를 리뉴얼했습니다.이 프로젝트에서 중점적으로 구현 하려고 했던 것은 기존 사이트에서 부족했던 디자인,동적, ui ux , 반응형 부분들이였습니다. 메인페이지를 좀 더 동적으로 디자인하여 축제라는 생동감 있는 컨텐츠들을 사용자들이 체감 할 수 있도록 표현 해줬습니다. 헤더 부분 또한 ui들이 난잡하여 접근성이 불편 하였는데 헤더의 내용들을 단축 시키고 필요한 서브 페이지들을 묶어 비교적 간단하게 구성 하였습니다.메인페이지의 전체적인 구성은 디자인적으로 트렌디한 첫섹션, 전체 축제들을 간략하게 소개할 수 있는 두번째 섹션,  가장 가까운 축제의 디데이와 간략한 내용으로 소개하는 세번째 섹션,공지사항과 새소식을 볼 수 있는 네번째 다섯번째 섹션, 주변 관광지를 소개 하는 여섯번째 섹션,패밀리사이트를 한눈에 보기쉽게 구성한 마지막 섹션으로 구성 했습니다.제가 이 웹사이트에서 기여한 부분은 메인페이지, 공지사항, 로그인, 회원가입, 이벤트 페이지입니다.",
        projectLink: "http://bfoc-env.eba-qmg3434g.ap-northeast-1.elasticbeanstalk.com/",
        gitLink: "https://github.com/potato980124/teamproject2",
        img1: require("../../public/img/teamproject.png"),
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
