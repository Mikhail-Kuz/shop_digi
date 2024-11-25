<template>
    <div class="price-select">
        <div class="price-select__title">Цена</div>
        <div class="price-select__inputs">
            <MyInput class="price-select__inputs__input"><template v-slot:icon>от</template></MyInput>
            <MyDivider />
            <MyInput class="price-select__inputs__input"><template v-slot:icon>до</template></MyInput>
        </div>
    </div>
</template>

<script>
import MyInput from './MyInput.vue';
import MyDivider from '../assets/icons/MyDivider.vue';

export default {
    name: 'PriceSelect',
    components: {
        MyInput,
        MyDivider,
    }
}
</script>

<style lang="scss" scoped>
    @import '../styles/colors';

    .price-select {
        margin-bottom: 28px;

        &__title {
            display: flex;
            justify-content: center;
            margin-bottom: 16px;
            font-weight: 700;
            font-size: 16px;
        }

        &__inputs {
            display: flex;
            align-items: center;
            
            &__input {
                width: 119px;
                border-color: $borderColor;
            }

            &__input:first-child {
                margin-right: 16px;
            }
            &__input:last-child {
                margin-left: 16px;
            }
        }
    }
</style>