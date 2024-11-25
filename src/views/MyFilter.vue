<template>
    <div class="filter">
        <MyMenu title="Название категории" count="0" :options="menuOptions" />
        <PriceSelect />
    </div>
</template>

<script>
import MyMenu from '../components/MyMenu/MyMenu.vue';
import PriceSelect from '../components/PriceSelect.vue';

export default {
    name: 'MyFilter',
    components: {
        MyMenu,
        PriceSelect,
    },

    data() {
        return {
            menuOptions: [
                { id: 1, title: 'Название категории', count: 3 },
                { id: 2, title: 'Название категории', count: 3 },
                { id: 3, title: 'Название категории', count: 3 },
            ],
        }
    }
}
</script>

<style lang="scss" scoped>
    @import '../styles/colors';

    .filter {
        width: 280px;

        display: flex;
        flex-direction: column;
        margin-right: 36px;

        & > * {
            font-family: "PT Sans";
            font-size: 14px;
            font-weight: 400;
            color: $fontPrimary;
        }
    }
</style>