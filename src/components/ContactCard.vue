<template>
  <div class="contact-card">
    <a :href="link" target="_blank" rel="noopener noreferrer">
      <img :src="require(`@/assets/${imgURL}`)" :alt="link" />
    </a>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";

@Options({
  props: {
    link: String,
    imgURL: String,
  },
})
export default class CareerCard extends Vue {
  link!: string;
  imgURL!: string;
}
</script>

<style lang="scss" scoped>
.contact-card img {
  background-color: white;
  width: 80px;
  height: 80px;
  border-radius: 50%;
  border: 2px solid white;
}

@media (min-width: 40rem) {
  .contact-card img {
    width: 100px;
    height: 100px;
  }
}
</style>
