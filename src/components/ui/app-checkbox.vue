<script setup>

import { defineProps } from 'vue'

const props = defineProps({
    title: String
})
</script>

<template>
    <!-- <label class="checkbox-wrapper" :for="props.title">
        <input type="checkbox" :id="props.title">
        <h6 class="checkbox__title">{{ props.title }}</h6>
    </label> -->
    <div class="control-group">
        <label class="control control-checkbox">
            {{props.title}}
            <input type="checkbox" checked="checked" />
            <div class="control_indicator"></div>
        </label>
    </div>
</template>

<style lang="scss">
.control {
    font-family: arial;
    display: block;
    position: relative;
    padding-left: 30px;
    margin-bottom: 5px;
    padding-top: 3px;
    cursor: pointer;
    font-size: 16px;
}

.control input {
    position: absolute;
    z-index: -1;
    opacity: 0;
}

.control_indicator {
    position: absolute;
    top: 2px;
    left: 0;
    height: 20px;
    width: 20px;
    background: #e6e6e6;
    border: 0px solid rgba(8, 62, 76, 0.50);
    border-radius: 4px;
}

.control:hover input~.control_indicator,
.control input:focus~.control_indicator {
    background: #cccccc;
}

.control input:checked~.control_indicator {
    background: #2aa1c0;
}

.control input:disabled~.control_indicator {
    background: #e6e6e6;
    opacity: 0.6;
    pointer-events: none;
}

.control_indicator:after {
    box-sizing: unset;
    content: '';
    position: absolute;
    display: none;
}

.control input:checked~.control_indicator:after {
    display: block;
}

.control-checkbox .control_indicator:after {
    left: 8px;
    top: 4px;
    width: 3px;
    height: 8px;
    border: solid #ffffff;
    border-width: 0 2px 2px 0;
    transform: rotate(45deg);
}

.control-checkbox input:disabled~.control_indicator:after {
    border-color: #7b7b7b;
}

.control-checkbox .control_indicator::before {
    content: '';
    display: block;
    position: absolute;
    left: 0;
    top: 0;
    width: 4.515rem;
    height: 4.361rem;
    margin-left: -1.149rem;
    margin-top: -1.061rem;
    background: #2aa1c0;
    border-radius: 3rem;
    opacity: 0.6;
    z-index: 99999;
    transform: scale(0);
}
</style>