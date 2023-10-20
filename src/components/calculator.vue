<script setup>

import AppRange from '@/components/ui/app-range.vue'
import AppMultipleRange from '@/components/ui/app-multiple-range.vue'
import AppCheckbox from '@/components/ui/app-checkbox.vue'
</script>

<template>
    <div class="calculator-body">
        <app-multiple-range :value1="6" :value2="6" :min="2" :max="6" title="Стоимость, млн ₽" />
        <div class="calculator-checkboxes">
            <app-checkbox title="Квартира" />
            <app-checkbox title="Апартамент" />
        </div>
        <app-range :modelValue="1000000" percentage="30%" title="Первоначальный взнос, ₽" />
        <app-range :modelValue="5" title="Срок выплат" />
    </div>
</template>

<style lang="scss">
.calculator-body {
    display: flex;
    flex-direction: column;
    gap: 35px;

    .calculator-checkboxes {
        display: flex;
        align-items: center;
        gap: 20px;

        @include breakpoint(xs) {
            flex-direction: column;
            align-items: flex-start;
        }
    }
}
</style>