<template>
    <div class="card" :class="!count && 'absent'">
        <div class="card__img">
            <div v-if="hit" class="card__img__hit">Хит продаж <IconHit /></div>
            <div v-if="discount" class="card__img__discount">{{ discount }}%</div>
            <IconBox />
        </div>
        <div class="card__brand">{{ brand }}</div>
        <div class="card__title">{{ publicTitle }}</div>
        <div v-if="count" class="card__price">
            <p>{{ price }} &#8381;</p>
            <p v-if="oldPrice">{{ oldPrice }} &#8381;</p>
        </div>
        <MyButton v-if="count" class="card__by">Купить</MyButton>
        <MyButton v-else class="card__info">Сообщить о поступлении</MyButton>
    </div>
</template>

<script>
import IconBox from '../assets/icons/IconBox.vue';
import IconHit from '../assets/icons/IconHit.vue';
import MyButton from '../components/MyButton.vue';

export default {
    name: 'MyCard',
    components:  {
        IconBox,
        MyButton,
        IconHit
    },
    props: {
        hit: Boolean,
        brand: {
            type: String,
            default: 'Бренд'
        },
        title: {
            type: String,
            default: 'Название'
        },
        price: {
            type: Number,
            default: 0
        },
        oldPrice: Number,
        discount: Number,
        count: Number,
    },
    computed: {
        publicTitle() {
            return this.title.slice(0, 67).concat('...')
        }
    }
}
</script>

<style lang="scss" scoped>
    @import '../styles/colors';

    .card {
        font-family: 'PT Sans';
        color: $fontPrimary;
        font-size: 14px;

        &__img {
            position: relative;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 200px;
            background-color: #F8F8FA;
            color: #A6A9C7;
            margin-bottom: 16px;

            &__hit {
                position: absolute;
                top: 12px;
                left: 12px;
                background-color: #ffffff;
                border-radius: 4px;
                border: 1px solid #F2F2F2;
                display: flex;
                align-items: center;
                padding: 8px;
                color: $fontPrimary;
                line-height: 16px;
            }

            &__discount {
                position: absolute;
                bottom: 12px;
                left: 12px;
                padding: 6px 10px;
                background-color: $primary;
                border-radius: 4px;
                color: #ffffff;
                line-height: 14px;
                font-weight: 700;
            }
        }

        &__brand {
            color: $fontGhost;
            margin-bottom: 8px;
        }

        &__title {
            margin-bottom: 16px;
        }

        &__price {
            display: flex;
            align-items: start;
            font-weight: 700;
            font-size: 16px;
            margin-bottom: 16px;

            & > p:last-child {
                margin-left: 8px;
                font-size: 12px;
                font-weight: 400;
                text-decoration: line-through;
                color: $fontGhost;
            }
        }

        &__by {
            font-family: 'PT Sans';
            color: $primary;
            font-weight: 700;
            padding: 12px 16px;
            line-height: 14px;
        }

        &.absent {
            .card__img {
                opacity: .5;
            }

            .card__info {
                width: 100%;
                display: flex;
                justify-content: center;
                border-color: $fontGhost;
                font-family: 'PT Sans';
                font-weight: 700;
                padding: 12px;
                line-height: 14px;
                color: $fontGhost;
                margin-top: 52px;
            }
        }

        &:hover {
            cursor: pointer;

            .card__img > svg {
                width: 82px;
                height: 82px;
            }

            .card__title {
                color: $primary;
            }
        }
    }
</style>