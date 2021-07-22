<template>
  <div class="project-card">
    <div class="project-card__logo">
      <img :src="require(`@/assets/${logoURL}`)" :alt="title" />
    </div>
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
    logoURL: String,
    link: String,
  },
})
export default class ProjectCard extends Vue {
  title!: string;
  logoURL!: string;
  link!: string;
}
</script>

<style lang="scss" scoped>
.project-card {
  display: grid;
  grid-template-areas:
    "title"
    "logo"
    "info"
    "link";
  border-bottom: 2px solid black;
  padding-bottom: 3rem;
  margin-bottom: 3rem;
  justify-content: center;
  align-items: center;
  justify-items: center;
  text-align: center;
}

.project-card__title {
  grid-area: title;
}

.project-card__link {
  grid-area: link;
}

.project-card__logo {
  grid-area: logo;
  img {
    width: 13rem;
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
    grid-template-columns: 1fr 2fr;
    grid-template-areas:
      "logo title"
      "logo info"
      "logo link";
    width: 50%;
    column-gap: 2rem;
    justify-items: left;
  }

  .project-card__info {
    text-align: left;
  }
}
</style>
