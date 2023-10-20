<script setup>
import { ref } from 'vue';

const props = defineProps({
    title: String,
    min: Number,
    max: Number,
    value1: Number,
    value2: Number
})

const value1 = ref(props.value1);
const value2 = ref(props.value2);

const updateValue1 = () => {
    emit('update:modelValue1', value1.value);
};

const updateValue2 = () => {
    emit('update:modelValue2', value2.value);
};
</script>
    
<template>
    <div class="inputs-wrapper">
        <h6 class="range__title">{{ props.title }}</h6>
        <div class="value-wrapper">
            <p>{{ value2 }}</p>
            <div class="separator"></div>
            <p>{{ value1 }}</p>
        </div>
        <input class="input-multiple first" type="range" :min="min" :max="max" v-model="value1" @input="updateValue1" />
        <input class="input-multiple" type="range" :min="min" :max="max" v-model="value2" @input="updateValue2" />
    </div>
</template>

<style lang="scss">
.inputs-wrapper {
    position: relative;

    &:hover {
        .value-wrapper {
            transition: all 0.3s;
            border: 1px solid #026D89;
        }
    }

    .value-wrapper {
        position: relative;
        display: flex;
        align-items: center;
        justify-content: space-between;
        padding: 20px;
        border-radius: 100px;
        border: 1px solid transparent;
        background: #F1F5F5;
        box-shadow: 0px 4px 15px 0px rgba(0, 0, 0, 0.02);

        .separator {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(50%, -50%);
            width: 2px;
            height: 15px;
            background: rgba(8, 62, 76, 0.50);
        }
    }

    input[type="range"] {
        -webkit-appearance: none;
        appearance: none;
        background: transparent;
        cursor: pointer;
    }

    /* Removes default focus */
    input[type="range"]:focus {
        outline: none;
    }

    /******** Chrome, Safari, Opera and Edge Chromium styles ********/
    /* slider track */
    input[type="range"]::-webkit-slider-runnable-track {
        background-color: #083e4c;
        border-radius: 0rem;
        height: 2px;
    }

    /* slider thumb */
    input[type="range"]::-webkit-slider-thumb {
        -webkit-appearance: none;
        /* Override default look */
        appearance: none;
        margin-top: -7px;
        /* Centers thumb on the track */
        background-color: #083e4c;
        border-radius: 10px;
        height: 16px;
        width: 16px;
    }

    input[type="range"]:focus::-webkit-slider-thumb {
        outline: 3px solid #083e4c;
        outline-offset: 0.125rem;
    }

    /*********** Firefox styles ***********/
    /* slider track */
    input[type="range"]::-moz-range-track {
        background-color: #083e4c;
        border-radius: 0rem;
        height: 2px;
    }

    .input-multiple {
        position: absolute;
        width: 180px;

        &.first {
            right: 0;
        }
    }
}
</style>
  
  