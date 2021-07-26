<template>
  <div class="backdrop" @click="closeSidebar"></div>
</template>

<script lang="ts">
import { Vue } from "vue-class-component";

export default class TheBackdrop extends Vue {
  closeSidebar() {
    const sidebar = document.querySelector(".mobile-nav") as HTMLDivElement;
    const backdrop = document.querySelector("#backdrop") as HTMLDivElement;
    backdrop.style.display = "none";
    sidebar.classList.remove("open");
  }
}
</script>

<style lang="scss" scoped>
.backdrop {
  display: none;
  position: fixed;
  top: 0;
  left: 0;
  z-index: 100;
  width: 100vw;
  height: 100vh;
  background: rgba(0, 0, 0, 0.5);
  transition: opacity 0.2s linear;
}
</style>
