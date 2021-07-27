<template>
  <div class="main-career">
    <div class="main-career__title">
      <h1>Career</h1>
    </div>
    <div class="main-career__items">
      <career-card
        title="BMSTU"
        time="June, 2020 - October, 2020"
        logoURL="bmstu.png"
        pos="Backend developer"
        ><p>
          Development of "Electronic university" infrastructure.<br /><br />

          Tech stack: <br />
          - TypeScrirpt (main development); <br />
          - Nest.js (backend); <br />
          - Angular (frontend); <br />
          - Pug (template engine); <br />
          - Swagger (API documentation); <br />
          - Postgres (main DB). <br /><br />

          Unit tests development and development of business-units for applicants personal account
          during BMSTU entrance at 2020.
        </p></career-card
      >
      <career-card
        title="Mail.Ru Group"
        time="October, 2020 - August, 2021"
        logoURL="mailru.png"
        pos="Highload systems developer"
        ><p>
          Enterprise development at Architecture & Presale department at B2B Tarantool.<br /><br />

          Tech stack: <br />
          - Go, Python (internal scripts); <br />
          - Lua (app developments); <br />
          - Tarantool (main DB); <br />
          - Postgres, ClickHouse, MongoDB (alternative DBs). <br /><br />

          Pilot projects development for external customers.
        </p></career-card
      >
      <career-card
        title="OZON"
        time="August, 2021 - to the present"
        logoURL="ozon.png"
        pos="Backend developer"
        ><p>
          Development of OZON Travel Railway platform.<br /><br />

          Tech stack: <br />
          - Go (backend); <br /><br />

          More to follow :)
        </p></career-card
      >
    </div>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import CareerCard from "@/components/CareerCard.vue";

@Options({ components: { CareerCard } })
export default class Career extends Vue {}
</script>

<style lang="scss" scoped>
.main-career {
  display: flex;
  width: 100vw;
  flex-direction: column;
  align-items: center;
  margin-bottom: 5rem;
}

.main-career__items {
  width: 80%;
  margin-left: auto;
  margin-right: auto;
}

@media (min-width: 40rem) {
  .main-career {
    margin-left: auto;
    margin-right: auto;
    width: 50vw;
  }

  .main-career__items {
    width: 50vw;
    margin-left: auto;
    margin-right: auto;
  }
}
</style>
