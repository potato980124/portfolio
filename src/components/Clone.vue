<template>
  <section class="clone">
    <div class="section_title">
      <h1 class="section_title_txt f32">👉 Clonecoding</h1>
    </div>
    <ul class="projects_cont_wrap">
      <li class="projects_cont" v-for="info in ClonesInfo" :key="info">
        <a href="">
          <div class="projects_cont_img">
            <img v-bind:src="info.img" alt="" />
          </div>
          <div class="projects_cont_txt">
            <h2 class="f22">{{ info.type }}</h2>
            <p class="f18">{{ info.title }}</p>
          </div>
        </a>
      </li>
    </ul>
  </section>
</template>
<script>
export default {
  setup() {
    let ClonesInfo = [
      {
        type: "클론코딩",
        title: "도시락통",
        img: require("../../public/img/dosirak.png"),
      },
      {
        type: "클론코딩",
        title: "더리치먼드 평창",
        img: require("../../public/img/rich.png"),
      },
      {
        type: "클론코딩",
        title: "싱그러운집",
        img: require("../../public/img/sing.png"),
      },
    ];
    return {
      ClonesInfo,
    };
  },
};
</script>
<style scoped></style>
