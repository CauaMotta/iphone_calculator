<script setup>
import { defineEmits, onMounted, onBeforeUnmount } from 'vue';

const emit = defineEmits(['btnClick']);

function getButton(event) {
    const buttonId = event.currentTarget ? event.currentTarget.id : event;

    emit('btnClick', buttonId);
}

function captureKey(event) {
    const keyMap = {
        '1': '1',
        '2': '2',
        '3': '3',
        '4': '4',
        '5': '5',
        '6': '6',
        '7': '7',
        '8': '8',
        '9': '9',
        '0': '0',
        '.': 'dot',
        ',': 'dot',
        '+': 'plus',
        '-': 'minus',
        '*': 'multiply',
        '/': 'divide',
        '=': 'equals',
        'Enter': 'equals',
        '%': 'percent',
        'Backspace': 'AC',
        'Delete': 'AC'
    };

    const buttonId = keyMap[event.key];
    if (buttonId) {
        getButton(buttonId);
    }
}

onMounted(() => {
    window.addEventListener('keydown', captureKey);
});

onBeforeUnmount(() => {
    window.removeEventListener('keydown', captureKey);
});

</script>

<template>
    <div class="keypad">

        <button id="AC" class="key gray" @click="getButton">AC</button>
        <button id="signal" class="key gray" @click="getButton"><i class="fa-solid fa-plus-minus"></i></button>
        <button id="percent" class="key gray" @click="getButton"><i class="fa-solid fa-percent"></i></button>
        <button id="divide" class="key orange" @click="getButton"><i class="fa-solid fa-divide"></i></button>

        <button id="7" class="key" @click="getButton">7</button>
        <button id="8" class="key" @click="getButton">8</button>
        <button id="9" class="key" @click="getButton">9</button>
        <button id="multiply" class="key orange" @click="getButton"><i class="fa-solid fa-xmark"></i></button>

        <button id="4" class="key" @click="getButton">4</button>
        <button id="5" class="key" @click="getButton">5</button>
        <button id="6" class="key" @click="getButton">6</button>
        <button id="minus" class="key orange" @click="getButton"><i class="fa-solid fa-minus"></i></button>

        <button id="1" class="key" @click="getButton">1</button>
        <button id="2" class="key" @click="getButton">2</button>
        <button id="3" class="key" @click="getButton">3</button>
        <button id="plus" class="key orange" @click="getButton"><i class="fa-solid fa-plus"></i></button>

        <button id="0" class="key zero" @click="getButton">0</button>
        <button id="dot" class="key" @click="getButton">,</button>
        <button id="equals" class="key orange" @click="getButton"><i class="fa-solid fa-equals"></i></button>

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
    font-size: 1.5rem;
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
    font-size: 1.25rem;
    font-weight: 400;
}

.orange {
    background-color: #FE9500;
    font-size: 1.25rem;
}
</style>
