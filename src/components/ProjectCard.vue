<template>
  <div class="project-card">
    <div class="project-card__title">
      <a :href="link">
        <h2>{{ title }}</h2>
      </a>
    </div>
    <div class="project-card__info">
      <slot>Very interesting project :)</slot>
    </div>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";

@Options({
  props: {
    title: String,
    link: String,
  },
})
export default class ProjectCard extends Vue {
  title!: string;
  link!: string;
}
</script>

<style lang="scss" scoped>
.project-card {
  display: flex;
  flex-direction: column;
  text-align: center;
  border: 2px solid black;
  padding: 3rem;
}

.project-card__title {
  a {
    text-decoration: none;
    color: grey;
    transition: 0.2s;
    &:hover,
    &:active {
      color: lightcoral;
    }
  }
}

.project-card__info {
  line-height: 1.5;
}

@media (min-width: 40rem) {
}
</style>
