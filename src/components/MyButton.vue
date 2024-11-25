<template>
    <button class="button" :class="buttonType">
        <div v-if="$slots.icon" class="button__icon">
            <slot name="icon" />
        </div>
        <slot />
    </button>
</template>

<script>
export default {
    name: 'MuButton',
    props: {
        buttonType: {
            type: String,
            default: 'default'
        }
    }
}
</script>

<style lang="scss" scoped>
@import '../styles/colors';

.button {
    padding: 12px 24px;
    display: flex;
    align-items: center;
    background-color: #ffffff;
    border: 1px solid $primary;
    border-radius: 8px;
    cursor: pointer;
    font-size: 14px;
    font-weight: 500;

    &:hover {
        background-color: transparentize($primary, .8);
    }

    &.ghost {
        border: none;
    }
    &.logo {
        border: none;

        &:hover {
            background-color: #ffffff;
        }
    }
    
    &__icon {
        display: flex;
        align-items: center;
        justify-content: center;
        margin-right: 8px;
    }
}
</style>