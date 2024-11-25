<template>
    <div class="checkbox-filter">
        <div class="checkbox-filter__title" :class="withClear && 'withClear'">
            <div class="checkbox-filter__title__name">{{ title }}</div>
            <div v-if="withClear" class="checkbox-filter__title__clear">Очистить</div>
        </div>
        <MyInput v-if="withSearch" class="checkbox-filter__search" placeholder="Поиск"><template v-slot:icon><IconSearch /></template></MyInput>
        <div v-if="options" class="checkbox-filter__group">
            <MyCheckbox 
                v-for="option in options" 
                :key="`${Date.now()}-${option.id}`" 
                :id="option.id"
                :label="option.title"
                :checked="option.checked"
                :count="option.count"
            />
        </div>
    </div>
</template>

<script>
import MyCheckbox from './MyCheckbox.vue';
import MyInput from './MyInput.vue';
import IconSearch from '../assets/icons/IconSearch.vue';

export default {
    name: 'CheckboxFilter',
    components: {
        MyCheckbox,
        MyInput,
        IconSearch
    },
    props: {
        title: {
            type: String,
            default: 'Название'
        }, 
        withSearch: Boolean,
        withClear: Boolean,
        options: Array,
    }
}
</script>

<style lang="scss">
    @import '../styles/colors';

    .checkbox-filter {
        margin-bottom: 28px;

        &__title {
            display: flex;
            justify-content: center;
            align-items: flex-end;
            margin-bottom: 16px;
            font-weight: 700;
            font-size: 16px;

            &.withClear {
                justify-content: space-between;
            }

            &__clear {
                font-size: 12px;
                font-weight: 400;
                color: $fontGhost;
                text-decoration: underline;
                cursor: pointer;

                &:hover {
                    color: $primary;
                }
            }
        }

        .input.checkbox-filter__search {
            border-color: $borderColor;
            border-radius: 4px;
            padding: 10px 12px;
            
        }

        &__search {
            margin-bottom: 16px;

            & > .input__icon svg {
                width: 16px;
                height: 16px;
            }

            & > input {
                height: 16px;
            }

            & > input::placeholder {
                font-size: 14px;
            }
        }

        &__group {
            max-height: 192px;
            overflow-y: auto;
            scrollbar-width: thin;
        }
    }
</style>