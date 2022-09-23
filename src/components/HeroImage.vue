<script setup>
const props = defineProps(['img', 'text', 'color'])
</script>

<template>
    <div class="img" :style="{ backgroundImage: 'url(' + props.img + ')' }">
        <div class="slant-top">
            <svg data-name="Layer 1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 120" preserveAspectRatio="none">
                <path d="M1200 120L0 16.48 0 0 1200 0 1200 120z" class="shape-fill"></path>
            </svg>
        </div>
        <h1 class="text" :style="{color: props.color}">{{ props.text }}</h1>

        <div class="slant-1">
            <svg data-name="Layer 1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 120" preserveAspectRatio="none">
                <path d="M1200 120L0 16.48 0 0 1200 0 1200 120z" class="shape-fill"></path>
            </svg>
        </div>

        <div class="slant-2">
            <svg data-name="Layer 1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 120" preserveAspectRatio="none">
                <path d="M1200 120L0 16.48 0 0 1200 0 1200 120z" class="shape-fill"></path>
            </svg>
        </div>

        <div class="slant-3">
            <svg data-name="Layer 1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 120" preserveAspectRatio="none">
                <path d="M1200 120L0 16.48 0 0 1200 0 1200 120z" class="shape-fill"></path>
            </svg>
        </div>
    </div>
</template>

<style scoped>

.img {
    background-color: var(--brand-orange);
    width: 100%;
    height: 500px;
    display: flex;
    align-items: center;
    justify-content: center;

    background-position: center;
    background-size: cover;
    background-repeat: no-repeat;

    position: relative;
}

.text {
    margin: 0;
    font-size: 72px;
    text-align: center;
    color: var(--brand-white);
}

@media screen and (max-width: 700px) {
  .text {
    font-size: 50px;
  }

  .img {
    background-position: 25%;
  }
}





.slant-1 {
    z-index: 90;
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    overflow: hidden;
    line-height: 0;
    transform: rotate(180deg);
    bottom: -1px;
}

.slant-1 svg {
    position: relative;
    display: block;
    width: calc(100% + 1.3px);
    height: 1.5vh;
}

.slant-1 .shape-fill {
    fill: #F3F3F3;
}

.slant-2 {
    z-index: 89;
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    overflow: hidden;
    line-height: 0;
    transform: rotate(180deg);
}

.slant-2 svg {
    position: relative;
    display: block;
    width: calc(100% + 1.3px);
    height: 3vh;
}

.slant-2 .shape-fill {
    fill: #FF5900;
}

.slant-3 {
    z-index: 88;
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    overflow: hidden;
    line-height: 0;
    transform: rotate(180deg);
}

.slant-3 svg {
    position: relative;
    display: block;
    width: calc(100% + 1.3px);
    height: 5vh;
}

.slant-3 .shape-fill {
    fill: #4D148C;
}

.slant-top {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    overflow: hidden;
    line-height: 0;
}

.slant-top svg {
    position: relative;
    display: block;
    width: calc(100% + 1.3px);
    height: 3.5vh;
}

.slant-top .shape-fill {
    fill: #4D148C;
}

</style>