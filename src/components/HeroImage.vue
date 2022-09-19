<script setup>
const props = defineProps(['img', 'text'])
</script>

<template>
    <div class="img" :style="{ backgroundImage: 'url(' + props.img + ')' }">
        <h1 class="text">{{ props.text }}</h1>
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
}

.text {
    margin: 0;
    font-size: 72px;
    color: var(--brand-white);
}

</style>