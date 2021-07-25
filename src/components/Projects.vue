<template>
  <div class="main-projects">
    <div class="main-projects__title">
      <h1>Projects</h1>
    </div>
    <div class="main-projects__items">
      <project-card
        id="project1"
        title="xk6-tarantool"
        link="https://github.com/hackfeed/xk6-tarantool"
        ><p>A k6 load testing utility extension for Tarantool</p></project-card
      >
      <project-card id="project2" title="mrratality" link="https://github.com/hackfeed/mrratality"
        ><p>MRR analytics system for SaaS-apps written in Go and Vue</p></project-card
      >
      <project-card
        id="project3"
        title="olegha-reddit-bot"
        link="https://github.com/hackfeed/olegha-reddit-bot"
        ><p>Telegram-bot for reddit fetching written in Python</p></project-card
      >
      <project-card
        id="project4"
        title="hackfeed.github.io-source"
        link="https://github.com/hackfeed/hackfeed.github.io-source"
        ><p>Source code of webpage you are visiting right now :)</p></project-card
      >
    </div>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import ProjectCard from "@/components/ProjectCard.vue";

@Options({ components: { ProjectCard } })
export default class Projects extends Vue {}
</script>

<style lang="scss" scoped>
.main-projects {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: 0 1rem;
  margin-bottom: 5rem;
}

.main-projects__items {
  display: flex;
  justify-content: center;
  flex-flow: wrap;
  margin-left: auto;
  margin-right: auto;
  gap: 2rem;
}

@media (min-width: 40rem) {
  #project2,
  #project4 {
    justify-content: right;
    justify-items: right;
  }

  .main-projects {
    margin-left: auto;
    margin-right: auto;
    width: 50%;
  }

  .main-projects__items > div {
    transition: 0.2s;
    &:hover,
    &:active {
      transform: scale(1.01);
      border-color: lightcoral;
    }
  }
}
</style>
