<template>
  <section class="about">
    <div class="about_title">
      <h1 class="f32">π μλνμΈμ, νλ‘ νΈμλ κ°λ°μ λ²μ§μλλ€!</h1>
    </div>
    <div class="about_cont">
      <aboutLeft></aboutLeft>
      <aboutRight></aboutRight>
    </div>
    <div class="about_cont2">
      <leftInfo></leftInfo>
      <rightInfo></rightInfo>
    </div>
  </section>
</template>
<script>
import aboutLeft from "./AboutMeLeft.vue";
import aboutRight from "./AboutMeRight.vue";
import leftInfo from "./LeftInfo.vue";
import rightInfo from "./RightInfo.vue";
export default {
  components: {
    aboutLeft,
    aboutRight,
    leftInfo,
    rightInfo,
  },
};
</script>
<style scoped>
.about_title {
  font-weight: bold;
  color: #424242;
  padding-bottom: 50px;
  box-sizing: border-box;
}
.about_cont {
  display: flex;
  gap: 190px;
  margin-bottom: 100px;
}
.about_cont2 {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}
.about_cont2 > div {
  width: calc(50% - 95px);
}
@media (max-width: 1300px) {
  .about_cont {
    display: flex;
    gap: 0;
    justify-content: space-between;
    margin-bottom: 100px;
  }
  .about_cont2 > div {
    width: 100%;
  }
}
@media (max-width: 1100px) {
  .about_cont {
    display: flex;
    flex-direction: column;
    margin-bottom: 100px;
  }
}

</style>
