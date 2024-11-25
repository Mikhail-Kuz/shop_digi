<template>
    <div class="menu__item" :class="active && 'active'">
        <div class="menu__item__title">{{ title }}</div>
        <div v-if="count" class="menu__item__count">{{ count }}</div>
    </div>
</template>

<script>
export default {
    name: 'MyMenuItem',
    props: {
        title: {
            type: String,
            default: 'Название'
        },
        count: Number,
        active: Boolean,
    }
}
</script>

<style lang="scss" scoped>
    @import '../../styles/colors';

    .menu__item {
        height: 30px;
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding-left: 32px;
        padding-right: 16px;
        border-radius: 5px;

        &.active {
            background-color: $colorActive;

            .menu__item__count {
                color: $fontPrimary;
            }
        }
        
        &:hover {
            background-color: transparentize($primary, .8);
        }

        &__count {
            font-size: 12px;
            color: $fontGhost;
        }
        
    }
</style>