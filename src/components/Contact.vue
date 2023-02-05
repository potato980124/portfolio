<template>
  <section class="contact">
    <div class="contact_bg">
      <div class="contact_title f60">CONTACT ME</div>
      <h2 class="mid_intro f32">
        도전을 멈추지 않고 배움을 즐기며<br />
        꾸준히 <strong class="strong_txt">성장하는 개발자가 되겠습니다.</strong
        ><br />
        아래버튼을 클릭하여 연락처를 확인해주세요.
      </h2>
      <div class="contact_box f20" v-if="contact == false" @click="clickConBox">
        연락처를 확인하세요!
      </div>
      <div class="contact_info_box f16" v-if="contact == true">
        <p>이름: 홍범진</p>
        <p>전화번호: 010-4752-3464</p>
        <p>이메일: potato980124@gmil.com</p>
      </div>
    </div>
    <div class="contact_img">
      <div class="c_img1"></div>
      <div class="c_img2"></div>
      <div class="c_img3"></div>
    </div>
  </section>
</template>
<script>
import { ref } from "vue";
export default {
  setup() {
    let contact = ref(false);
    let clickConBox = function () {
      contact.value = true;
    };
    return {
      contact,
      clickConBox,
    };
  },
};
</script>
<style scoped>
.contact {
  position: relative;
}
.contact_title {
  font-weight: bold;
}
.mid_intro {
  margin: 25px 0 50px 0;
}
.contact_box {
  width: fit-content;
  color: #fff;
  background-color: #333333;
  border-radius: 10px;
  padding: 10px 80px;
  box-sizing: border-box;
  cursor: pointer;
}
.strong_txt {
  color: #007aff;
}
.contact_info_box {
  width: fit-content;
  border-radius: 10px;
  background-color: #333333;
  color: #fff;
  padding: 20px 30px;
  box-sizing: border-box;
}
.contact_info_box > p:nth-child(2) {
  margin: 5px 0;
}
.c_img1{
    position: absolute;
    top: 20%;
    right: 0;
    width: 400px;
    height: 400px;
    background-image: url(../../public/img/firstround.png);
    z-index: -3;
    background-size: cover;
}
.c_img2{
    position: absolute;
    bottom: 0;
    right: 0;
    width: 700px;
    height: 700px;
    background-image: url(../../public/img/secondround.png);
    z-index: -2;
    background-size: cover;
}
.c_img3{
    position: absolute;
    bottom: 0;
    right: 0;
    width: 40vw;
    height: 40vh;
    background-image: url(../../public/img/contactimogi.png);
    background-repeat: no-repeat;
    background-size: contain;
    background-position: center center;
    z-index: -1;
}
@media(max-width:1300px){
    .c_img3{
        display: none;
    }
}
</style>
