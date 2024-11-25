<template>
    <div class="filter">
        <MyMenu title="Название категории" count="0" :options="menuOptions" />
        <PriceSelect />
        <CheckboxFilter title="Бренд" :options="brandOptions" withClear withSearch />
        <CheckboxFilter title="Размер" :options="sizeOptions" />
    </div>
</template>

<script>
import MyMenu from '../components/MyMenu/MyMenu.vue';
import PriceSelect from '../components/PriceSelect.vue';
import CheckboxFilter from '../components/CheckboxFilter.vue';

export default {
    name: 'MyFilter',
    components: {
        MyMenu,
        PriceSelect,
        CheckboxFilter
    },

    data() {
        return {
            menuOptions: [
                { id: 1, title: 'Название категории', count: 3 },
                { id: 2, title: 'Название категории', count: 3 },
                { id: 3, title: 'Название категории', count: 3 },
            ],
            brandOptions: [
                { id: 1, title: 'Атрибут', checked: true, count: 3 },
                { id: 2, title: 'Атрибут', checked: false, count: 3 },
                { id: 3, title: 'Атрибут', checked: false, count: 3 },
                { id: 4, title: 'Атрибут', checked: false, count: 3 },
                { id: 5, title: 'Атрибут', checked: false, count: 3 },
                { id: 6, title: 'Атрибут', checked: false, count: 3 },
                { id: 7, title: 'Атрибут', checked: false, count: 3 },
                { id: 8, title: 'Атрибут', checked: false, count: 3 },
                { id: 9, title: 'Атрибут', checked: false, count: 3 },
            ],
            sizeOptions: [
                { id: 1, title: 'Атрибут', checked: false, count: 3 },
                { id: 2, title: 'Атрибут', checked: false, count: 3 },
                { id: 3, title: 'Атрибут', checked: false, count: 3 },
                { id: 4, title: 'Атрибут', checked: false, count: 3 },
                { id: 5, title: 'Атрибут', checked: false, count: 3 },
                { id: 6, title: 'Атрибут', checked: false, count: 3 },
            ]
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