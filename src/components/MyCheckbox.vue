<template>
    <div class="checkbox">
        <input :id="id" class="checkbox__input" type="checkbox" :checked="checked" />
        <label :for="id" class="checkbox__label">{{ label }}</label>
        <div v-if="count" class="checkbox__count">{{ count }}</div>
    </div>
</template>

<script>
export default {
    name: 'MyCheckbox',
    props: {
        id: Number,
        label: String,
        checked: Boolean,
        count: Number
    }

}
</script>

<style lang="scss" scoped>
    @import '../styles/colors';

    .checkbox {
        display: flex;
        align-items: center;
        margin-bottom: 12px;

        &__input {
            appearance: none;
            position: relative;
            width: 20px;
            height: 20px;
            cursor: pointer;
            border: 1px solid $borderColor;
            border-radius: 3px;
            margin-right: 12px;
    
            &:checked {
                background: $primary;
                border-color: $primary;
            }
    
            &::after {
                content: "\2714";
                position: absolute;
                top: -2px;
                left: 2px;
                width: 0px;
                height: 0px;
                font-size: 16px;
                color: #ffffff;
                overflow: hidden;
            }
    
            &:checked::after {
                width: 20px;
                height: 20px;   
            }
        }

        &__label {
            flex: 1 1 auto;
            cursor: pointer;
        }

        &__count {
            flex: 0 0 auto;
            color: $fontGhost;
            font-size: 12px;
        }
    }
</style>