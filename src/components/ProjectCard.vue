<template>
  <div class="project-card">
    <div class="project-card__title">
      <h2>{{ title }}</h2>
    </div>
    <div class="project-card__info">
      <slot>Very interesting project :)</slot>
    </div>
    <div class="project-card__link">
      Read more: <a :href="link">{{ link }}</a>
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
  display: grid;
  grid-template-areas:
    "title"
    "info"
    "link";
  border: 2px solid black;
  padding: 3rem;
  justify-content: center;
  align-items: center;
  justify-items: center;
  text-align: center;
  width: 100%;
}

.project-card__link {
  grid-area: link;
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
  grid-area: info;
  text-align: center;
  line-height: 1.5;
}

@media (min-width: 40rem) {
  .project-card {
    text-align: left;
    justify-content: left;
    justify-items: left;
  }

  .project-card__info {
    text-align: left;
  }
}
</style>
