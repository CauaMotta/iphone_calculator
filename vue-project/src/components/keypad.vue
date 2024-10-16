<script setup>
import { reactive } from 'vue';

const data = reactive({
    number: '0',
})

function addNumber(number) {
    data.number += number;
    console.log(data.number)
}
function clearNumber() {
    data.number = '0';
}
</script>

<template>
    <div class="keypad">

        <button class="key gray" @click="clearNumber()">AC</button>
        <button class="key gray"><i class="fa-solid fa-plus-minus"></i></button>
        <button class="key gray"><i class="fa-solid fa-percent"></i></button>
        <button class="key orange"><i class="fa-solid fa-divide"></i></button>


        <!-- Numpad -->
        <button class="key" @click="addNumber(7)">7</button>
        <button class="key" @click="addNumber(8)">8</button>
        <button class="key" @click="addNumber(9)">9</button>
        <button class="key orange"><i class="fa-solid fa-xmark"></i></button>


        <button class="key" @click="addNumber(4)">4</button>
        <button class="key" @click="addNumber(5)">5</button>
        <button class="key" @click="addNumber(6)">6</button>
        <button class="key orange"><i class="fa-solid fa-minus"></i></button>


        <button class="key" @click="addNumber(1)">1</button>
        <button class="key" @click="addNumber(2)">2</button>
        <button class="key" @click="addNumber(3)">3</button>
        <button class="key orange"><i class="fa-solid fa-plus"></i></button>


        <button class="key zero" @click="addNumber(0)">0</button>
        <button class="key">,</button>
        <button class="key orange"><i class="fa-solid fa-equals"></i></button>

    </div>
</template>

<style scoped>
.keypad {
    display: grid;
    gap: .5rem;
    grid-template-columns: repeat(4, 1fr);
}

.key {
    width: 40px;
    height: 40px;
    border-radius: 50%;
    border: 0;
    cursor: pointer;
    background-color: #343434;
    color: #ccc;
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