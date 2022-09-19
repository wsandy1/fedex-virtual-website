<script setup>

import { onMounted, reactive, computed } from 'vue';

import HeroImage from '../components/HeroImage.vue';
import Stat from '../components/Stat.vue';

const stats_data = reactive({ routes: 0, aircraft: 0, pilots: 0 });

onMounted(() => {
  fetch("https://vamsys.io/statistics/70c81980-4852-43e2-8eda-b5b2512fca87")
  .then((res) => res.json())
  .then((data) => {
    stats_data.routes = data.general.routes;
    stats_data.aircraft = data.general.aircraft;
    stats_data.pilots = data.pilots.total;
  })
});

</script>

<template>
  <HeroImage img="/src/assets/images/homehero.jpg" text="The World of Virtual Time"></HeroImage>
  <main>
    <div class="stats-row">
      <Stat :value="stats_data.routes" header="Routes" icon="/src/assets/icons/route.svg"/>
      <Stat :value="stats_data.aircraft" header="Aircraft" icon="/src/assets/icons/airplane.svg"/>
      <Stat :value="stats_data.pilots" header="Pilots" icon="/src/assets/icons/person.svg"/>
    </div>
  </main>
</template>

<style scoped>
  main {
    padding-top: 50px;
    max-width: 60%;
    margin: 0 auto;
  }

  .stats-row {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
</style>

