<script setup>
import display from './display.vue';
import keypad from './keypad.vue';
</script>

<template>
    <div class="iphone">
        <display />
        <keypad />
    </div>
</template>

<style scoped>
.iphone {
    background-color: #000;
    padding: 5rem .5rem 3rem .5rem;
    border-radius: 1rem;
    border: 3px solid #fff;
}
</style>