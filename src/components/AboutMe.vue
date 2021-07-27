<template>
  <div class="main-aboutme">
    <div class="main-aboutme__title">
      <h1>About me</h1>
    </div>
    <div class="main-aboutme__photo">
      <img src="@/assets/profile.jpg" alt="Sergey Kononenko" />
    </div>
    <div class="main-aboutme__bio">
      <p>
        BMSTU student, fullstack developer.<br />
        Currently studying on ICS7, 4th year of education.<br />
        Working at OZON since August, 2021.<br />
        Backend-developer at OZON Travel.
      </p>
    </div>
  </div>
</template>

<script lang="ts">
import { Vue } from "vue-class-component";

export default class AboutMe extends Vue {}
</script>

<style lang="scss" scoped>
.main-aboutme {
  display: grid;
  width: 100%;
  grid-template-areas:
    "title"
    "photo"
    "bio";
  margin-bottom: 5rem;
  justify-content: center;
  align-items: center;
  justify-items: center;
  gap: 2rem;
}

.main-aboutme__title {
  grid-area: title;
}

.main-aboutme__photo {
  grid-area: photo;
  img {
    width: 20rem;
    height: 20rem;
    object-fit: cover;
    object-position: 0% 25%;
    border-radius: 10rem;
    border: 2px black solid;
  }
}

.main-aboutme__bio {
  grid-area: bio;
  p {
    text-align: center;
    line-height: 1.5;
  }
}

@media (min-width: 40rem) {
  .main-aboutme {
    grid-template-areas:
      "title title"
      "photo bio";
  }

  .main-aboutme__bio p {
    text-align: left;
  }
}
</style>
