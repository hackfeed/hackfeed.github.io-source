<template>
  <div class="main-projects">
    <div class="main-projects__title">
      <h1>Projects</h1>
    </div>
    <project-card
      title="xk6-tarantool"
      logoURL="k6.png"
      link="https://github.com/hackfeed/xk6-tarantool"
      ><p>A k6 extension for tarantool</p></project-card
    >
    <project-card
      title="xk6-tarantool"
      logoURL="k6.png"
      link="https://github.com/hackfeed/xk6-tarantool"
      ><p>A k6 extension for tarantool</p></project-card
    >
    <project-card
      title="xk6-tarantool"
      logoURL="k6.png"
      link="https://github.com/hackfeed/xk6-tarantool"
      ><p>A k6 extension for tarantool</p></project-card
    >
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
</style>
