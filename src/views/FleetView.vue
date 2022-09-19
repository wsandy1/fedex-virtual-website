<script setup>
import HeroImage from '../components/HeroImage.vue';

</script>

<template>
    <HeroImage img="/src/assets/images/fleethero.png" text="Fleet"/>
    <main>
        <h1>Fly your own way with our diverse fleet</h1>
        <div class="aircraft">
            <img src="../assets/images/a300.jpg" alt="">
            <div class="aircraft-details">
                <h1>A300</h1>
                <p>WIDE-BODY</p>
            </div>
        </div>

        <div class="aircraft">
            <img src="../assets/images/md11.jpg" alt="">
            <div class="aircraft-details">
                <h1>MD-11</h1>
                <p>WIDE-BODY TRI-JET</p>
            </div>
        </div>

        <div class="aircraft">
            <img src="../assets/images/737.jpg" alt="">
            <div class="aircraft-details">
                <h1>737</h1>
                <p>NARROW-BODY</p>
            </div>
        </div>

        <div class="aircraft">
            <img src="../assets/images/757.jpg" alt="">
            <div class="aircraft-details">
                <h1>757</h1>
                <p>NARROW-BODY</p>
            </div>
        </div>

        <div class="aircraft">
            <img src="../assets/images/767.jpg" alt="">
            <div class="aircraft-details">
                <h1>767</h1>
                <p>NARROW-BODY</p>
            </div>
        </div>

        <div class="aircraft">
            <img src="../assets/images/777.jpg" alt="">
            <div class="aircraft-details">
                <h1>777</h1>
                <p>WIDE-BODY</p>
            </div>
        </div>

        <div class="aircraft">
            <div class="aircraft-details">
                <h1>DC-10</h1>
                <p>HISTORICAL WIDE-BODY TRI-JET</p>
            </div>
        </div>

        <div class="aircraft">
            <div class="aircraft-details">
                <h1>DC-10</h1>
                <p>HISTORICAL WIDE-BODY TRI-JET</p>
            </div>
        </div>

        <div class="aircraft">
            <div class="aircraft-details">
                <h1>ATR 42/72</h1>
                <p>REGIONAL TURBOPROP</p>
            </div>
        </div>
    </main>

</template>

<style scoped>

.aircraft {
    display: flex;
    align-items: center;
    margin-bottom: 40px;
}

.aircraft img {
    width: 50%;
}

.aircraft .aircraft-details {
    width: 50%;
    margin-left: 50px;
}

.aircraft-details h1 {
    margin: 0;
}

.aircraft-details p {
    margin: 0;
    color: var(--brand-orange);
}

</style>