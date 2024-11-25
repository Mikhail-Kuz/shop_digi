<template>
    <div class="menu">
        <div class="menu__title">
            <div class="menu__title__name">
                {{ title }}
            </div>
            <div v-if='count' class="menu__title__count">{{ count }}</div>
        </div>
        <div v-show="open && options" class="menu__options">
            <MyMenuItem v-for="option in options" :key="option.id" :title="option.title" :count="option.count" :active="option.id === activeId" />
        </div>
    </div>
</template>

<script>
import MyMenuItem from './MyMenuItem.vue';

export default {
    name: 'MyMenu',
    components: {
        MyMenuItem
    },
    props: {
        title: {
            type: String,
            default: 'Название'
        },
        count: Number,
        options: Array,
    },
    
    data() {
        return {
            open: true,
            activeId: 1,
        }
    }
}
</script>

<style lang="scss" scoped>
    @import '../../styles/colors';

    .menu {
        cursor: pointer;
        margin-bottom: 28px;

        &__title {
            height: 30px;
            display: flex;
            justify-content: space-between;
            padding-left: 8px;
            padding-right: 16px;
            border-radius: 5px;

            &:hover {
                background-color: transparentize($primary, .8);
            }

            &__name, &__count {
                display: flex;
                align-items: center;
            }

            &__count {
                font-size: 12px;
                color: $fontGhost;
            }
        }
    }
</style>