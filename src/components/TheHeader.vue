<template>
  <header class="main-header">
    <div>
      <button class="toggle-button" @click="openSidebar">
        <span class="toggle-button__bar"></span>
        <span class="toggle-button__bar"></span>
        <span class="toggle-button__bar"></span>
      </button>
      <a href="/" class="main-header__logo"
        ><img src="@/assets/logo.png" alt="hackfeed's Webpage"
      /></a>
    </div>
    <nav class="main-nav">
      <ul class="main-nav__items">
        <li class="main-nav__item">
          <a
            v-scroll-to="{
              el: '#about-me',
              offset: -48,
            }"
            >About me</a
          >
        </li>
        <li class="main-nav__item">
          <a
            v-scroll-to="{
              el: '#career',
              offset: -48,
            }"
            >Career</a
          >
        </li>
        <li class="main-nav__item">
          <a
            v-scroll-to="{
              el: '#projects',
              offset: -48,
            }"
            >Projects</a
          >
        </li>
        <li class="main-nav__item">
          <a
            v-scroll-to="{
              el: '#contacts',
              offset: -48,
            }"
            >Contacts</a
          >
        </li>
      </ul>
    </nav>
  </header>
  <nav class="mobile-nav">
    <ul class="mobile-nav__items">
      <li class="mobile-nav__item">
        <a
          v-scroll-to="{
            el: '#about-me',
            offset: -48,
          }"
          @click="closeSidebar"
          >About me</a
        >
      </li>
      <li class="mobile-nav__item">
        <a
          v-scroll-to="{
            el: '#career',
            offset: -48,
          }"
          @click="closeSidebar"
          >Career</a
        >
      </li>
      <li class="mobile-nav__item">
        <a
          v-scroll-to="{
            el: '#projects',
            offset: -48,
          }"
          @click="closeSidebar"
          >Projects</a
        >
      </li>
      <li class="mobile-nav__item">
        <a
          v-scroll-to="{
            el: '#contacts',
            offset: -48,
          }"
          @click="closeSidebar"
          >Contacts</a
        >
      </li>
    </ul>
  </nav>
</template>

<script lang="ts">
import { Vue } from "vue-class-component";

export default class TheHeader extends Vue {
  openSidebar() {
    const sidebar = document.querySelector(".mobile-nav") as HTMLDivElement;
    const backdrop = document.querySelector("#backdrop") as HTMLDivElement;
    backdrop.style.display = "block";
    sidebar.classList.add("open");
  }
  closeSidebar() {
    const sidebar = document.querySelector(".mobile-nav") as HTMLDivElement;
    const backdrop = document.querySelector("#backdrop") as HTMLDivElement;
    backdrop.style.display = "none";
    sidebar.classList.remove("open");
  }
}
</script>

<style lang="scss" scoped>
$full-size: 100vw;

.main-header {
  width: $full-size;
  position: fixed;
  top: 0;
  left: 0;
  background: white;
  border-bottom: 2px solid black;
  padding: 0.5rem 1rem;
  z-index: 10;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.main-header__logo {
  color: black;
  text-decoration: none;
  font-weight: bold;

  img {
    height: 2.5rem;
    vertical-align: middle;
  }
}

.toggle-button {
  width: 3rem;
  background: transparent;
  border: none;
  cursor: pointer;
  padding-top: 0;
  padding-bottom: 0;
  vertical-align: middle;

  &:focus {
    outline: none;
  }
}

.toggle-button__bar {
  width: 100%;
  height: 0.2rem;
  background: black;
  display: block;
  margin: 0.6rem 0;
}

.main-nav {
  display: none;
}

.main-nav__items {
  margin: 0;
  padding: 0;
  list-style: none;
  display: flex;
}

.main-nav__item {
  margin: 0 1rem;

  a {
    text-decoration: none;
    color: black;
    font-weight: bold;
    padding: 0.2rem 0;
    transition: 0.2s;
    &:hover,
    &:active {
      cursor: pointer;
      color: lightcoral;
    }
  }
}

.mobile-nav {
  transform: translateX(-100%);
  transition: transform 0.2s ease-out;
  position: fixed;
  z-index: 101;
  top: 0;
  left: 0;
  background: white;
  width: 80%;
  height: 100%;
  border-right: 2px solid black;
}

.mobile-nav__items {
  width: 90%;
  height: 100%;
  list-style: none;
  margin: auto;
  padding: 0;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.mobile-nav__item {
  margin: 1rem 0;

  a {
    font-size: 1.5rem;
    text-decoration: none;
    color: black;
    font-weight: bold;
    padding: 0.2rem 0;
    &:active {
      color: lightcoral;
    }
  }
}

.open {
  display: block !important;
  transform: translateY(0) !important;
}

@media (min-width: 40rem) {
  .toggle-button {
    display: none;
  }

  .main-nav {
    display: flex;
  }
}
</style>
