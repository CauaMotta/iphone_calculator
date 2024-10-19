<script setup>
import { defineEmits } from 'vue';

const emit = defineEmits(['btnClick']);

function getButton(event) {
    const buttonId = event.target.id;

    emit('btnClick', buttonId);
}
</script>

<template>
    <div class="keypad">

        <button class="key gray">AC</button>
        <button class="key gray"><i class="fa-solid fa-plus-minus"></i></button>
        <button class="key gray"><i class="fa-solid fa-percent"></i></button>
        <button class="key orange"><i class="fa-solid fa-divide"></i></button>


        <!-- Numpad -->
        <button id="7" class="key" @click="getButton">7</button>
        <button id="8" class="key" @click="getButton">8</button>
        <button id="9" class="key" @click="getButton">9</button>
        <button class="key orange"><i class="fa-solid fa-xmark"></i></button>


        <button id="4" class="key" @click="getButton">4</button>
        <button id="5" class="key" @click="getButton">5</button>
        <button id="6" class="key" @click="getButton">6</button>
        <button class="key orange"><i class="fa-solid fa-minus"></i></button>


        <button id="1" class="key" @click="getButton">1</button>
        <button id="2" class="key" @click="getButton">2</button>
        <button id="3" class="key" @click="getButton">3</button>
        <button class="key orange"><i class="fa-solid fa-plus"></i></button>


        <button id="0" class="key zero" @click="getButton">0</button>
        <button class="key">,</button>
        <button class="key orange"><i class="fa-solid fa-equals"></i></button>

    </div>
</template>

<style scoped>
.keypad {
    width: 100%;
    display: grid;
    justify-content: center;
    gap: .75rem;
    grid-template-columns: repeat(4, auto);
    padding-bottom: 1.5rem;
}

.key {
    width: 56px;
    height: 56px;
    border-radius: 50%;
    border: 0;
    cursor: pointer;
    background-color: #343434;
    color: #ccc;
    font-size: 1.25rem;
}

.zero {
    width: 100%;
    border-radius: 2rem;
    grid-column-start: 1;
    grid-column-end: 3;
    text-align: start;
    padding-left: 1rem;
}

.gray {
    color: #000;
    background-color: #A4A4A4;
}

.orange {
    background-color: #FE9500;
}
</style>