<script setup>
import { reactive, defineProps, watch, defineEmits } from 'vue';

const props = defineProps(['defineKey'])
const emit = defineEmits(['resetKey'])
const data = reactive({
    number: 0,
    showNumber: '0',
    operation: '',
})

function calculator() {
    switch (props.defineKey) {
        case 'equals':
            switch (data.operation) {
                case 'plus':
                case 'minus':
                case 'multiply':
                case 'divide':
                case 'percent':
                    math(data.operation);
                    break;
            }
            data.operation = '';
            break;
        case 'plus':
        case 'minus':
        case 'multiply':
        case 'divide':
        case 'percent':
            math(props.defineKey);
            break;
        case 'dot':
            data.showNumber += ',';
            break;
        case 'signal':
            if (data.showNumber.includes('-')) {
                const newValue = data.showNumber.slice(1);
                data.showNumber = newValue;
            } else {
                data.showNumber = '-' + data.showNumber;
            }
            break;
        case 'AC':
            data.showNumber = '0';
            break;
        default:
            if (data.showNumber === '0' || data.showNumber == data.number) {
                data.showNumber = props.defineKey != '' ? props.defineKey : data.showNumber;
            } else {
                data.showNumber += props.defineKey;
            }
            break;
    }
    resetValue();
}

function math(operation) {
    if (data.operation === '') {
        data.number = parseFloat(data.showNumber.replace(',', '.'));
        data.operation = operation;
        data.showNumber = '0';
    } else if (data.operation === operation) {
        switch (operation) {
            case 'plus':
                data.number = data.number + parseFloat(data.showNumber.replace(',', '.'));
                break;
            case 'minus':
                data.number = data.number - parseFloat(data.showNumber.replace(',', '.'));
                break;
            case 'multiply':
                data.number = data.number * parseFloat(data.showNumber.replace(',', '.'));
                break;
            case 'divide':
                data.number = data.number / parseFloat(data.showNumber.replace(',', '.'));
                break;
            case 'percent':
                data.number = (data.number * parseFloat(data.showNumber.replace(',', '.'))) / 100;
                break;
        }
        data.showNumber = data.number.toString().replace('.', ',');
    }
}

function resetValue() {
    return emit('resetKey', '');
}

watch(() => props.defineKey, () => calculator());

</script>

<template>
    <p class="display">{{ data.showNumber }}</p>
</template>

<style scoped>
.display {
    color: #fff;
    text-align: end;
    font-size: 3rem;
    font-weight: 300;
    width: 100%;
    padding-right: 2rem;
    padding-bottom: 1rem;
}
</style>