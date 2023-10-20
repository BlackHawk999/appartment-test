<script setup>

import { RESULT_INFO } from '@/common/constants'
</script>

<template>
    <div class="result">
        <div class="result__corner">
            <div class="result__corner-wrapper">
                <svg class="result__corner-icon" width="349" height="65" viewBox="0 0 349 65" fill="none"
                    xmlns="http://www.w3.org/2000/svg">
                    <path
                        d="M348 0.1875C348 0.1875 135.121 0 0 0C15 0.5 19.5017 8.1875 29.5017 22.1875C39.5017 36.1875 54.0017 36.1875 54.0017 36.1875C54.0017 36.1875 303 35.875 319 36.1875C335 36.5 348.5 49.5 349 65L348 0.1875Z"
                        fill="white" />
                </svg>
                <p class="result__corner-text">
                    Узнайте о других <span>интересных предложениях</span>
                </p>
            </div>
        </div>

        <div class="result-wrapper">
            <h2 class="result__title">Ипотека 0.1%</h2>
            <div class="result-infos">
                <div class="result-child" v-for="item in RESULT_INFO" :key="item.title">
                    <p class="child__pretitle">{{ item.pretitle }}</p>
                    <h5 class="child__title">{{ item.title }}</h5>
                </div>
            </div>
        </div>
    </div>
</template>

<style lang="scss">
.result {
    position: relative;
    width: 100%;
    overflow: hidden;

    &-wrapper {
        border-radius: 16px;
        background-color: #083E4C;
        padding: 20px;
        display: flex;
        flex-direction: column;
        gap: 50px;

        @include breakpoint(sm) {
            gap: 30px;
        }
    }

    &__title {
        width: fit-content;
        padding: 12px 15px;
        font-size: 74px;
        line-height: 110%;
        color: #083E4C;
        background: #fff;
        border-radius: 16px;

        @include breakpoint(lg) {
            margin-top: 30px;
        }

        @include breakpoint(md) {
            font-size: 65px;
        }

        @include breakpoint(sm) {
            font-size: 50px;
        }

        @include breakpoint(xs) {
            margin-top: 15px;
            font-size: 25px;
        }
    }

    &-infos {
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        gap: 65px;

        @include breakpoint(md) {
            gap: 50px;
        }

        @include breakpoint(sm) {
            gap: 35px;
        }

        @include breakpoint(xs) {
            grid-template-columns: repeat(2, 1fr);
            gap: 15px;
        }
    }

    &-child {
        display: flex;
        flex-direction: column;
        gap: 15px;

        @include breakpoint(sm) {
            gap: 10px;
        }

        @include breakpoint(xs) {
            align-items: center;
        }
    }

    .child {
        &__pretitle {
            color: rgba(255, 255, 255, 0.70);
            font-size: 14px;
            line-height: 100%;
        }

        &__title {
            color: #FFF;
            font-size: 30px;
            line-height: 120%;

            @include breakpoint(md) {
                font-size: 25px;
            }

            @include breakpoint(sm) {
                font-size: 20px;
            }

            @include breakpoint(xs) {
                font-size: 16px;
            }
        }
    }

    &__corner {
        position: absolute;
        top: -1px;
        right: -1px;
        height: 80px;
        width: 425px;

        &-wrapper {
            position: relative;
            display: flex;
            align-items: center;
            justify-content: center;
            width: 100%;
            height: 100%;
        }

        &-text {
            position: absolute;
            top: 15px;
            font-size: 14px;
            font-weight: 500;
            color: #3D4543;

            @include breakpoint(sm) {
                top: 5px;
                right: 10px;
                color: #fff;
            }

            span:hover {
                color: #083E4C;
                cursor: pointer;

                @include breakpoint(xs) {
                    color: rgba(0, 91, 115, 1);
                }
            }
        }

        &-icon {
            width: 100%;
            height: 100%;

            @include breakpoint(sm) {
                display: none;
            }
        }
    }
}
</style>