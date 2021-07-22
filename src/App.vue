<template>
  <the-header></the-header>
  <main>
    <about-me id="about-me"></about-me>
    <career id="career"></career>
    <projects id="projects"></projects>
  </main>
  <the-footer></the-footer>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import TheHeader from "@/components/TheHeader.vue";
import TheFooter from "@/components/TheFooter.vue";
import AboutMe from "@/components/AboutMe.vue";
import Career from "@/components/Career.vue";
import Projects from "@/components/Projects.vue";
@Options({
  components: { TheHeader, TheFooter, AboutMe, Career, Projects },
})
export default class App extends Vue {}
</script>

<style lang="scss">
@import url(https://fonts.googleapis.com/css?family=Montserrat:400,700);

$full-size: 100%;

* {
  box-sizing: border-box;
}

html {
  height: $full-size;
}

body {
  font-family: "Montserrat", sans-serif;
  margin: 0;
  height: $full-size;
}

#app {
  display: grid;
  grid-template-rows: 3.5rem auto fit-content(8rem);
  grid-template-areas:
    "header"
    "main"
    "footer";
  height: $full-size;
}

main {
  grid-area: main;
}
</style>
