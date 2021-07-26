<template>
  <div class="main-contacts">
    <div class="main-contacts__title">
      <h1>Contacts</h1>
    </div>
    <div class="main-contacts__items">
      <contact-card
        imgURL="hh.png"
        link="https://hh.ru/resume/d1931d07ff05aa99b80039ed1f515a52507774"
      ></contact-card>
      <contact-card
        imgURL="email.png"
        link="mailto:hackfeed@yandex.ru"
      ></contact-card>
      <contact-card
        imgURL="github.png"
        link="https://github.com/hackfeed"
      ></contact-card>
      <contact-card
        imgURL="telegram.png"
        link="https://t.me/hackfeed"
      ></contact-card>
    </div>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import ContactCard from "@/components/ContactCard.vue";

@Options({ components: { ContactCard } })
export default class Career extends Vue {}
</script>

<style lang="scss" scoped>
.main-contacts {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: 0 1rem;
  margin-bottom: 5rem;
}

.main-contacts__items {
  display: flex;
  justify-content: center;
  > div {
    margin: 0 0.3rem;
    transition: 0.2s;
    &:hover,
    &:active {
      transform: scale(1.2);
    }
  }
}

@media (min-width: 40rem) {
  .main-contacts {
    margin-left: auto;
    margin-right: auto;
    width: 50%;
  }
}
</style>
