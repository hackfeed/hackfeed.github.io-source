<template>
  <div class="job-card">
    <div class="job-card__title">
      <h2>{{ title }}</h2>
    </div>
    <div class="job-card__time">
      <h3>{{ time }}</h3>
    </div>
    <div class="job-card__logo">
      <img :src="require(`@/assets/${logoURL}`)" :alt="title" />
    </div>
    <div class="job-card__pos">
      <h3>{{ pos }}</h3>
    </div>
    <div class="job-card__info">
      <slot>Just worked :)</slot>
    </div>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";

@Options({
  props: {
    title: String,
    time: String,
    pos: String,
    logoURL: String,
  },
})
export default class CareerCard extends Vue {
  title!: string;
  time!: string;
  pos!: string;
  logoURL!: string;
}
</script>

<style lang="scss" scoped>
.job-card {
  display: grid;
  grid-template-areas:
    "title"
    "time"
    "logo"
    "pos"
    "info";
  border-bottom: 2px solid black;
  padding-bottom: 3rem;
  margin-bottom: 3rem;
  justify-content: center;
  align-items: center;
  justify-items: center;
  text-align: center;
  width: 100%;
}

.job-card__title {
  grid-area: title;
}

.job-card__time {
  grid-area: time;
}

.job-card__logo {
  grid-area: logo;
  img {
    width: 13rem;
  }
}

.job-card__pos {
  grid-area: pos;
}

.job-card__info {
  grid-area: info;
  text-align: center;
  line-height: 1.5;
}

@media (min-width: 40rem) {
  .job-card {
    text-align: left;
    grid-template-columns: 1fr 2fr;
    grid-template-areas:
      "title pos"
      "time info"
      "logo info";
    column-gap: 2rem;
    justify-items: left;
  }

  .job-card__info {
    text-align: left;
  }
}
</style>
