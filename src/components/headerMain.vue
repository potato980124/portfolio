<template>
  <header class="f14">
    <nav class="padding80">
      <div class="logo_txt">🎉활기찬,코딩🎉</div>
      <ul class="gnb">
        <li @click="goSection" data-target="about" class="gotosection">
          About Me
        </li>
        <li @click="goSection" data-target="projects" class="gotosection">
          Projects
        </li>
        <li @click="goSection" data-target="clone" class="gotosection">
          CloneCoding
        </li>
        <li @click="goSection" data-target="contact" class="gotosection">
          Contact
        </li>
      </ul>
    </nav>
  </header>
</template>

<script>
export default {
  setup() {
    const goSection = function (e) {
      e.preventDefault();
      if (!e.target.matches(".gotosection")) return;
      const sec = document.getElementsByClassName(e.target.dataset.target)[0];
      console.log(sec);
      if (sec) {
        sec.scrollIntoView({ behavior: "smooth" });
      }
    };
    return {
      goSection,
    };
  },
};
</script>

<style scoped>
header {
  height: 60px;
  line-height: 60px;
  font-weight: 700;
  border-bottom: 1px solid #f5f5f5;
  background-color: #fff;
}
nav {
  display: flex;
  justify-content: space-between;
}
.gnb {
  display: flex;
  gap: 40px;
}
.gnb > li {
  cursor: pointer;
}
</style>
