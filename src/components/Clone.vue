<template>
  <section class="clone">
    <div class="section_title">
      <h1 class="section_title_txt f32">๐ Clonecoding</h1>
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
        type: "ํด๋ก ์ฝ๋ฉ",
        title: "๋์๋ฝํต",
        img: require("../../public/img/dosirak.png"),
      },
      {
        type: "ํด๋ก ์ฝ๋ฉ",
        title: "๋๋ฆฌ์น๋จผ๋ ํ์ฐฝ",
        img: require("../../public/img/rich.png"),
      },
      {
        type: "ํด๋ก ์ฝ๋ฉ",
        title: "์ฑ๊ทธ๋ฌ์ด์ง",
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
