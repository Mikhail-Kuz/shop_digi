<template>
    <div class="header">
        <MyButton class="header__logo" buttonType="logo">
            <template #icon><IconLogo class="header__logo__icon" /></template>
            Логотип
        </MyButton>
        <MyButton>Каталог</MyButton>
        <MyInput class="header__search" placeholder="Поиск по 100 000 товаров">
            <template v-slot:icon><IconSearch /></template>
        </MyInput>
        <div class="header__links">
            <a href="#">Информация о компании</a>
            <a href="#">Контакты</a>
            <a href="#">Полезные ссылки</a>
        </div>
    </div>
</template>

<script>
import IconLogo from '../assets/icons/IconLogo.vue'
import IconSearch from '../assets/icons/IconSearch.vue'
import MyButton from '../components/MyButton.vue'
import MyInput from '../components/MyInput.vue'

export default {
    name: 'MyHeader',
    components: {
        IconLogo,
        IconSearch,
        MyButton,
        MyInput,
    }
}
</script>

<style lang="sass" scoped>
    @import '../styles/colors';

    .header {
        display: flex;
        align-items: strech;
        margin: 0 100px;
        margin-bottom: 24px;
        padding: 12px 0;

        & > * {
            font-family: 'Inter';
        }

        &__logo {
            display: flex;
            align-items: center;
            font-size: 16px;
            font-weight: 400;
            margin-right: 8px;

            &__icon {
                color: $primary;
            }
        }

        &__search {
            flex: 1;
            margin: 0 24px;
        }

        &__links {
            display: flex;
            align-items: center;

            & > a {
                text-decoration: none;
                color: $fontPrimary;

                &:not(:last-child) {
                    margin-right: 20px;
                }

                &:hover {
                    color: $primary;
                }
            }
        }
    }
</style>