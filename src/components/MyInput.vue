<template>
    <div class="input">
        <input type="text" :placeholder="placeholder" />
        <div v-if="$slots.icon" class="input__icon">
            <slot name="icon" />
        </div>
    </div>
</template>

<script>
export default {
    name: 'MyInput',
    props: {
        placeholder: String,
    }
}
</script>

<style lang="scss" scoped>
@import '../styles/colors';

.input {
    border: 1px solid $primary;
    border-radius: 10px;
    display: flex;
    flex-direction: row-reverse;
    justify-content: start;
    align-items: center;
    padding: 12px 16px;

    & > input {
        width: 100%;
        outline: 0;
        border: none;
        font-size: 16px;
        padding: 0 8px;
    }

    &__icon {
        display: flex;
        align-items: center;
        justify-content: center;
        color: $ghost;
    }

    & > input:focus ~ .input__icon {
        color: $primary;
    }
}
</style>