<script setup>
import { defineProps } from 'vue'
import AppButton from '@/components/ui/app-button.vue'

const props = defineProps({
  title: String,
  image: String,
  text: String

})
</script>

<template>
  <div class="card">
    <div class="card-wrapper">
      <div class="card__img">
        <img :src="props.image" alt="">
      </div>
      <h3 class="card__title">{{ props.title }}</h3>
      <div class="card-button-wrapper">
        <app-button class="card__btn">
          <svg width="24" height="24" viewBox="0 0 24 24" fill="#fff" xmlns="http://www.w3.org/2000/svg">
            <path fill-rule="evenodd" clip-rule="evenodd" d="M7 4V20L20 12L7 4Z" stroke="#fff" stroke-width="2"
              stroke-linecap="round" stroke-linejoin="round" />
          </svg>
        </app-button>
      </div>
      <p class="card__text">{{ props.text }}</p>
    </div>
  </div>
</template>

<style lang="scss">
.card {
  flex: 1;
  height: 300px;
  width: 400px;
  max-height: 300px;
  max-width: 550px;

  @include breakpoint(md) {
    width: 350px;
  }

  @include breakpoint(sm) {
    width: 300px;
  }

  &-wrapper {
    position: relative;
    transition: all 0.3s;
    cursor: pointer;

    &:hover {
      .card__title {
        color: #FFF;
        background: #083E4C;
        transition: all 0.3s;

      }

      .card__img {
        img {
          transform: scale(1.05);
          transition: all 0.3s;
        }
      }

      .card__btn {
        transform: rotate(90deg);
        background: rgba(0, 91, 115, 1);
        transition: all 0.3s;
      }
    }
  }

  &__img {
    position: relative;
    width: 400px;
    height: 300px;
    z-index: 9;
    border-radius: 16px;
    overflow: hidden;

    @include breakpoint(md) {
    width: 350px;
  }

  @include breakpoint(sm) {
    width: 300px;
  }

    img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }

    &::after {
      content: "";
      position: absolute;
      top: 0;
      right: 0;
      left: 0;
      bottom: 0;
      background: linear-gradient(0deg, rgba(0, 0, 0, 0.70) 31.33%, rgba(0, 0, 0, 0.00) 59.93%);
    }
  }

  &__title {
    position: absolute;
    top: 5%;
    left: 5%;
    padding: 10px 12px;
    font-size: 26px;
    line-height: 130%;
    border-radius: 10px;
    color: #545863;
    background: #FFF;
    z-index: 10;
  }

  &-button-wrapper {
    position: absolute;
    bottom: 0%;
    right: 0%;
    padding: 10px 0 0 10px;
    z-index: 10;
    background: #FFF;
    border-radius: 34px 0 0 34px;

    &::before {
      content: "";
      position: absolute;
      right: 0;
      bottom: 0;
      background: #FFF;
      width: 5px;
      height: 5px;
    }

    &::after {
      content: "";
      position: absolute;
      right: 0;
      bottom: 0;
      background: #ffffff;
      width: 5px;
      height: 3px;
    }
  }

  &__btn {
    width: 60px;
    height: 60px;
    display: flex;
    align-items: center;
    justify-content: center;
    background: #083E4C;
    border: 1px solid #083E4C;
    border-radius: 50%;
    outline: none;
  }

  &__text {
    position: absolute;
    left: 5%;
    bottom: 10%;
    width: 80%;
    padding-top: 15px;
    color: #FFF;
    border-top: 1px solid #FFF;
    z-index: 10;
  }
}
</style>