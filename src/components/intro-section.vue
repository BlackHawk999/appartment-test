<script setup >

import { CARD_ARR } from '@/common/constants'
import AppButton from '@/components/ui/app-button.vue'
import Card from '@/components/card.vue'
import Calculator from '@/components/calculator.vue';
import Result from '@/components/result.vue';

</script>

<template>
    <div class="intro">
        <div class="intro-header">
            <h2 class="header__title">Варианты покупки</h2>
            <div class="header-actions">
                <app-button class="header-info__btn">
                    Подробнее
                </app-button>
                <app-button class="header__btn previous">
                    <svg width="24" height="24" viewBox="0 0 24 24" fill="#083E4C" xmlns="http://www.w3.org/2000/svg">
                        <path fill-rule="evenodd" clip-rule="evenodd" d="M7 4V20L20 12L7 4Z" stroke="#083E4C"
                            stroke-width="2" stroke-linecap="round" stroke-linejoin="round" />
                    </svg>
                </app-button>
                <app-button class="header__btn">
                    <svg width="24" height="24" viewBox="0 0 24 24" fill="#083E4C" xmlns="http://www.w3.org/2000/svg">
                        <path fill-rule="evenodd" clip-rule="evenodd" d="M7 4V20L20 12L7 4Z" stroke="#083E4C"
                            stroke-width="2" stroke-linecap="round" stroke-linejoin="round" />
                    </svg>
                </app-button>
            </div>
        </div>
        <div class="intro-cards-wrapper">
            <card v-for="card in CARD_ARR" :key="card.title" :title="card.title" :image="card.image" :text="card.text" />
        </div>
        <div class="intro-body">
            <div class="intro-calculator">
                <h3 class="calculator__title">Ипотечный калькулятор</h3>
                <calculator />
            </div>
            <div class="intro-result">
                <result />
                <p class="intro-result__subtitle">
                    Приведенные расчеты носят предварительный характер. Окончательный расчет
                    суммы кредита и размер ежемесячного платежа производится банком после предоставления оценки
                    платежеспособности клиента.
                </p>
                <app-button class="intro-result__btn">Подать заявку на точный расчёт</app-button>
            </div>
        </div>
    </div>
</template>

<style lang="scss">
.intro {
    display: flex;
    flex-direction: column;
    width: 100%;
    height: 100vh;
    padding: 50px;
    background: #fff;

    @include breakpoint(sm) {
        padding: 25px;
    }

    @include breakpoint(xs) {
        padding: 15px;
    }


    &-header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        width: 100%;
    }

    .header {
        &__title {
            font-size: 42px;
            line-height: 120%;
            color: #3D4543;


            @include breakpoint(md) {
                font-size: 35px;
            }

            @include breakpoint(sm) {
                font-size: 25px;
            }

            @include breakpoint(xs) {
                margin-right: 8px;
                font-size: 16px;
            }
        }

        &-actions {
            display: flex;
            align-items: center;

        }

        &-info__btn {
            padding: 20px 25px;
            margin-right: 20px;
            font-weight: 500;
            line-height: 100%;
            background: transparent;
            color: #083E4C;
            border: 1px solid #083E4C;
            border-radius: 34px;
            outline: none;
            cursor: pointer;

            @include breakpoint(md) {
                padding: 20px;
            }

            @include breakpoint(sm) {
                padding: 15px;
                margin-right: 10px;
            }

            @include breakpoint(xs) {
                padding: 10px;
            }

            &:hover {
                transition: all 0.3s;
                color: #FFF;
                background: #083E4C;
            }
        }

        &__btn {
            display: flex;
            align-items: center;
            justify-content: center;
            height: 60px;
            width: 60px;
            padding: 20px;
            background: transparent;
            border: 1px solid #083E4C;
            border-radius: 50%;
            transition: all 0.2s;
            cursor: pointer;

            @include breakpoint(md) {
                height: 50px;
                width: 50px;
            }

            @include breakpoint(sm) {
                height: 40px;
                width: 40px;
                padding: 15px;
            }

            &:hover {
                background: #083E4C;

                svg path {
                    fill: #FFF;
                }
            }

            &.previous {
                margin-right: 12px;

                @include breakpoint(sm) {
                    margin-right: 8px;
                }

                svg {
                    transform: rotate(180deg);
                }
            }
        }
    }

    &-cards-wrapper {
        display: flex;
        align-items: center;
        flex-wrap: wrap;
        gap: 35px;
        margin-top: 35px;

        @include breakpoint(md) {
            justify-content: center;
        }
    }

    &-body {
        display: flex;
        gap: 40px;
        margin-top: 75px;

        @include breakpoint(md) {
            flex-direction: column;
            align-items: center;
        }
    }

    &-calculator {
        width: 430px;
        max-width: 430px;
        padding: 25px 35px 35px 35px;
        border-radius: 40px;
        border: 1px solid #083E4C;

        @include breakpoint(xs) {
            width: 100%;
        }

        &:hover {
            .calculator__title {
                transition: all 0.3s;
                background: #083E4C;
            }
        }
    }

    .calculator {

        &__title {
            width: fit-content;
            padding: 10px;
            margin-bottom: 30px;
            color: #FFF;
            font-size: 14px;
            line-height: 100%;
            border-radius: 10px;
            background: rgba(8, 62, 76, 0.50);
        }
    }

    &-result {
        display: flex;
        flex-direction: column;
        align-items: center;
        flex: 1;
    }

    &-result__subtitle {
        margin-top: 25px;
        font-size: 14px;
        color: #778478;
    }

    &-result__btn {
        padding: 20px 25px;
        margin-top: 40px;
        line-height: 100%;
        border-radius: 34px;
        color: #fff;
        background: #083E4C;
        outline: none;
        border: none;
        transition: all 0.3s;
        cursor: pointer;

        &:hover {
            background: rgba(0, 91, 115, 1);
        }
    }
}
</style>