<script setup>

    import { onMounted, computed, ref } from 'vue';
    import VueNumber from 'vue-number-animation';
import Number from '../../node_modules/vue-number-animation/Number.vue';

    const props = defineProps(['header', 'value', 'icon', 'cta'])
    const stat_value = ref(0)

    function kformat(number) {
        const formatter = Intl.NumberFormat('en', { notation: 'compact' });
        return formatter.format(number);
    }
</script>

<template>
    <div class="wrapper">
        <img v-if="props.icon" :src="props.icon"/>
        <div class="main">
            <h2><Number :from="0" :to="props.value" :format="kformat" easing="Power2.easeOut" :duration="5"/></h2>
            <p class="header">{{props.header}}</p>
        </div>
    </div>
</template>

<style scoped>
    .wrapper {
        display: flex;
        align-items: center;
        width: 25%;

    }
    .header {
        font-family: "FuturaBold";
        margin: 0;
        color: var(--brand-purple);
        font-size: 24px;
    }

    .main {
        display: flex;
        flex-direction: column;
        margin-left: 10px;
    }

    h2 {
        margin: 0;
        color: var(--brand-orange);
        font-size: 96px;
        line-height: 1;
    }

    img {
        width: 80px;
        height: 80px;
    }
</style>