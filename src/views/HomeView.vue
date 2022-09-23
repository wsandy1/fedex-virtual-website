<script setup>

import { onMounted, reactive, computed, ref, Transition } from 'vue';

import HeroImage from '../components/HeroImage.vue';
import Stat from '../components/Stat.vue';

const stats_data = reactive({ routes: 0, aircraft: 0, pilots: 0 });
const show_chevron = ref(true);

onMounted(() => {
  window.addEventListener('scroll', () => {
    var scrollTop = window.pageYOffset || (document.documentElement || document.body.parentNode || document.body).scrollTop;
    show_chevron.value = scrollTop === 0 ? true : false;
  })

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
  

  <Transition>
    <div v-if="show_chevron" class="container">
      <div class="chevron"></div>
      <div class="chevron"></div>
      <div class="chevron"></div>
    </div>
  </Transition>


  <HeroImage img="/src/assets/images/homehero.jpg" text="The World on Virtual Time"></HeroImage>
  <main>
    <div class="stats-row">
      <Stat :value="stats_data.routes" header="Routes" icon="/src/assets/icons/route.svg"/>
      <Stat :value="stats_data.aircraft" header="Aircraft" icon="/src/assets/icons/airplane.svg"/>
      <Stat :value="stats_data.pilots" header="Pilots" icon="/src/assets/icons/person.svg"/>
    </div>
    <h1>Welcome to the world's biggest (virtual) cargo airline.</h1>
    <div class="content-halves">
      <div class="about">
        <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quae doloremque eveniet molestias? Autem quaerat nulla cumque est. Odit in ducimus corporis inventore id et eveniet error eaque! Blanditiis, facere in.
        Laboriosam, ducimus hic accusantium repellendus ea libero corporis sint perspiciatis deserunt consequatur! Omnis modi adipisci consectetur perspiciatis. Voluptate autem vel iure modi facilis quia quod! Fugit minus assumenda rerum modi.</p>
        <RouterLink to="/fleet" class="arrow-button">SEE THE FLEET</RouterLink>
      </div>
      <img src="../assets/images/homeimage.jpg"/>
    </div>
  </main>
  <div class="promo">
    <a class="promo-box" href="https://vamsys.io/register/dhlvirtual">
      <div class="promo-content">
        <p>JOIN OUR PARTNER AIRLINE</p>
        <img src="../assets/images/dhl.png"/>
      </div>
    </a>
    <a class="promo-box" href="https://vamsys.io/register/upsvirtual">
      <div class="promo-content">
        <p>JOIN OUR PARTNER AIRLINE</p>
        <img src="../assets/images/ups.png"/>
      </div>
    </a>
  </div>
</template>

<style scoped>
  .stats-row {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 120px;
    margin-top: 105px;
  }

  @media screen and (max-width: 750px) {
  .stats-row {
    flex-direction: column;
    margin-top: 75px;
  }
}

  .container {
  position: fixed;
  width: 100%;
  height: 24px;
  bottom: 8vh;
  display: flex;
  justify-content: center;
  transition: display 3s;
}

.chevron {
  position: absolute;
  width: 60px;
  height: 15px;
  opacity: 0;
  transform: scale3d(0.5, 0.5, 0.5);
  animation: move 3s ease-out infinite;
}

.chevron:first-child {
  animation: move 3s ease-out 1s infinite;
}

.chevron:nth-child(2) {
  animation: move 3s ease-out 2s infinite;
}

.chevron:before,
.chevron:after {
  content: ' ';
  position: absolute;
  top: 0;
  height: 100%;
  width: 51%;
  background: var(--brand-orange);
}

.chevron:before {
  left: 0;
  transform: skew(0deg, 30deg);
}

.chevron:after {
  right: 0;
  width: 50%;
  transform: skew(0deg, -30deg);
}

@keyframes move {
  25% {
    opacity: 1;

  }
  33% {
    opacity: 1;
    transform: translateY(20px);
  }
  67% {
    opacity: 1;
    transform: translateY(40px);
  }
  100% {
    opacity: 0;
    transform: translateY(60px) scale3d(0.5, 0.5, 0.5);
  }
}

@keyframes pulse {
  to {
    opacity: 1;
  }
}

.v-enter-active,
.v-leave-active {
  transition: opacity 0.5s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}

.content-halves {
  display: flex;
  align-items: center;
}

.content-halves .about {
  width: 50%;
  font-family: "Roboto";
  line-height: 1.7;
  padding: 20px;
}

.content-halves .about .arrow-button {
  margin-right: 30px;
}

.content-halves img {
  width: 50%;
}


@media screen and (max-width: 1000px) {
  .content-halves {
    flex-direction: column-reverse;
  }

  .content-halves .about {
    width: auto;
  }

  .content-halves img {
    width: 100%;
  }
}

.promo {
  width: 100%;
  display: flex;
  margin-top: 80px;
}

.promo-box {
  padding: 25px;
}

.promo-box:first-child .promo-content {
  float: right;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.promo-box img {
  width: 300px;
}


@media screen and (max-width: 750px) {
    .promo-box img {
        max-width: 100%;
    }
}

.promo-box:first-child {
  background-color: #fecc00;
  width: 50%;
  color: #d40511;
}

.promo-box:last-child {
  background: #262425;
  width: 50%;
  color: #fcfcfc;
}

.promo-box:last-child .promo-content {
  float: left;
  display: flex;
  flex-direction: column;
  align-items: center;
}

</style>

