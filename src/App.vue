<template>
  <headerMain></headerMain>
  <main class="padding80">
    <AboutMe></AboutMe>
    <Projects></Projects>
    <Clone></Clone>
    <Contact></Contact>
  </main>
</template>

<script>
import headerMain from "./components/headerMain.vue";
import AboutMe from "./components/AboutMe.vue";
import Projects from "./components/Projects.vue";
import Clone from "./components/Clone.vue";
import Contact from "./components/Contact.vue";

export default {
  name: "App",
  components: {
    headerMain,
    AboutMe,
    Projects,
    Clone,
    Contact,
  },
};
</script>

<style scoped>
header {
  width: 100%;
  position: fixed;
  z-index: 999;
}
main {
  padding-top: 110px;
}
section {
  height: 100vh;
}
</style>
