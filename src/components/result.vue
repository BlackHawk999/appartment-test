<script setup>

import { RESULT_INFO } from '@/common/constants'
</script>

<template>
    <div class="result">
        <!-- <div class="result-corner"></div> -->
        <div class="result-wrapper">
            <h2 class="result__title">Ипотека 0.1%</h2>
            <div class="result-infos">
                <div class="result-child" v-for="item in RESULT_INFO" :key="item.title">
                    <p class="child__pretitle">{{ item.pretitle }}</p>
                    <h5 class="child__title">{{ item.title }}</h5>
                </div>
            </div>
        </div>
        <!-- <svg style="visibility: hidden; position: absolute;" width="0" height="0" xmlns="http://www.w3.org/2000/svg"
            version="1.1">
            <defs>
                <filter id="goo">
                    <feGaussianBlur in="SourceGraphic" stdDeviation="8" result="blur" />
                    <feColorMatrix in="blur" mode="matrix" values="1 0 0 0 0  0 1 0 0 0  0 0 1 0 0  0 0 0 19 -9"
                        result="goo" />
                    <feComposite in="SourceGraphic" in2="goo" operator="atop" />
                </filter>
            </defs>
        </svg> -->
    </div>
</template>

<style lang="scss">
.result {
    position: relative;
    padding: 20px;
    clip-path: polygon(0% 0%, 63% 0%, 74% 14%, 100% 14%, 100% 100%, 0% 100%);
    color: white;
    z-index: 2;
    background-color: #083E4C;
    border-radius: 16px;

    &-wrapper {
        display: flex;
        flex-direction: column;
        gap: 50px;
    }

    &__title {
        width: fit-content;
        padding: 12px 15px;
        font-size: 74px;
        line-height: 110%;
        color: #083E4C;
        background: #fff;
        border-radius: 16px;
    }

    &-infos {
        display: flex;
        align-items: center;
        gap: 65px;
    }

    &-child {
        display: flex;
        flex-direction: column;
        gap: 15px;
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
        }
    }

    // &-corner {
    //     float: right;
    //     display: inline-blog;
    //     width: 100px;
    //     height: 40px;
    //     margin-right: -5px;
    //     background: white;
    //     border-bottom-left-radius: 20px;
    //     position: relative;
    //     transform: skew(20deg);
    // }

    // &-corner::before {
    //     content: '';
    //     background: blue;
    //     width: 20px;
    //     height: 20px;
    //     position: absolute;
    //     border-top: 10px solid white;
    //     border-right: 10px solid white;
    //     border-top-right-radius: 20px;
    //     right: calc(100% - 10px);
    //     top: -10px;
    // }

    // &-corner::after {
    //     content: '';
    //     background: blue;
    //     width: 20px;
    //     height: 20px;
    //     position: absolute;
    //     border-top: 10px solid white;
    //     border-right: 10px solid white;
    //     border-top-right-radius: 20px;
    //     right: 4px;
    //     top: calc(100% - 10px);
    //     transform: skew(-20deg);
    // }
}
</style>