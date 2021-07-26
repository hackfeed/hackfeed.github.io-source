<template>
  <footer class="main-footer">
    <nav>
      <ul class="main-footer__links">
        <li class="main-footer__link">
          Designed and developed by
          <a href="https://github.com/hackfeed" target="_blank">@hackfeed</a>
        </li>
      </ul>
    </nav>
  </footer>
</template>

<script lang="ts">
import { Vue } from "vue-class-component";
export default class TheFooter extends Vue {}
</script>

<style lang="scss" scoped>
.main-footer {
  background: white;
  border-top: 2px solid black;
  padding: 0.5rem 1rem;
  grid-area: footer;
}

.main-footer__links {
  list-style: none;
  margin: 0;
  padding: 0;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.main-footer__link {
  margin: 0.5rem 0;
  a {
    color: grey;
    text-decoration: none;
    transition: color 0.3s ease-out;
    &:hover,
    &:active {
      color: lightcoral;
    }
  }
}
</style>
