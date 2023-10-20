<script setup lang="ts">
import { defineProps, ref } from 'vue'

const props = defineProps({
  modelValue: Number,
  title: String,
  percentage: String,
  maxValue: Number,
  minValue: Number
})

const emit = defineEmits(['update:modelValue'])

const value = ref(props.modelValue)

const updateValue = (event) => {
  value.value = event.target.value;
  emit('update:modelValue', value.value);
}
</script>

<template>
  <div class="range-wrapper">
    <h6 class="range__title">{{ props.title }}</h6>
    <div class="value-wrapper">
      <p class="value">{{ props.modelValue }}</p>
      <div v-if="props.percentage" class="separator"></div>
      <p class="value">{{ props.percentage }}</p>
    </div>
    <input class="range__input" type="range" v-model="value" @input="updateValue">
  </div>
</template>

<style lang="scss">
.range-wrapper {
  position: relative;
  &:hover {
    .value-wrapper {
      transition: all 0.3s;
      border: 1px solid #026D89;
    }
  }

  .range__title {
    font-size: 14px;
    line-height: 100%;
    color: #3D4543;
    margin-bottom: 13px;
  }

  .value {
    &-wrapper {
      position: relative;
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 20px;
      border-radius: 50px;
      border: 1px solid transparent;
      background: #F1F5F5;
      box-shadow: 0px 4px 15px 0px rgba(0, 0, 0, 0.02);

      @include breakpoint(sm) {
        width: 100%;
      }

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
  }

  .range__input {
    position: absolute;
    left: 7%;

    @include breakpoint(sm) {
      left: 0;
    }
  }

  input[type="range"] {
    -webkit-appearance: none;
    appearance: none;
    background: transparent;
    cursor: pointer;
    width: 315px;

    @include breakpoint(sm) {
      width: 100%;
    }
  }

  input[type="range"]:focus {
    outline: none;
  }

  input[type="range"]::-webkit-slider-runnable-track {
    background-color: #083e4c;
    border-radius: 0rem;
    height: 2px;
  }

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

  input[type="range"]::-moz-range-track {
    background-color: #083e4c;
    border-radius: 0rem;
    height: 2px;
  }

}
</style>