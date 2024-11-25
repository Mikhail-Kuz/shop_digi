<template>
    <div class="catalog">
        <MyCard 
            v-for="card in cards" 
            :key="`card-${card.id}`"
            :hit="card.hit"
            :brand="card.brand"
            :title="card.title"
            :price="card.price"
            :oldPrice="card.oldPrice"
            :discount="card.discount"
            :count="card.count"
        />
    </div>
</template>

<script>
import MyCard from '../components/MyCard.vue';

export default {
    name: 'MyCatalog',
    components: {
        MyCard,
    },

    data() {
        return {
            cards: [
                { id: 1, hit: true, brand: 'Бренд', title: 'Полное название товара в несколько строк для вида с обрывом в конце Полное название товара в несколько строк для вида с обрывом в конце', price: 5990, oldPrice: 5990, discount: 25, count: 123 }, 
                { id: 2, hit: true, brand: 'Бренд', title: 'Полное название товара в несколько строк для вида с обрывом в конце Полное название товара в несколько строк для вида с обрывом в конце', price: 5990, oldPrice: 5990, discount: 25, count: 123 }, 
                { id: 3, hit: true, brand: 'Бренд', title: 'Полное название товара в несколько строк для вида с обрывом в конце Полное название товара в несколько строк для вида с обрывом в конце', price: 5990, oldPrice: 5990, discount: 25, count: 0 }, 
                { id: 4, hit: true, brand: 'Бренд', title: 'Полное название товара в несколько строк для вида с обрывом в конце Полное название товара в несколько строк для вида с обрывом в конце', price: 5990, oldPrice: 5990, discount: 25, count: 123 }, 
                { id: 5, hit: true, brand: 'Бренд', title: 'Полное название товара в несколько строк для вида с обрывом в конце Полное название товара в несколько строк для вида с обрывом в конце', price: 5990, oldPrice: 5990, discount: 25, count: 123 }, 
                { id: 6, hit: true, brand: 'Бренд', title: 'Полное название товара в несколько строк для вида с обрывом в конце Полное название товара в несколько строк для вида с обрывом в конце', price: 5990, oldPrice: 5990, discount: 25, count: 123 }, 
                { id: 7, hit: true, brand: 'Бренд', title: 'Полное название товара в несколько строк для вида с обрывом в конце Полное название товара в несколько строк для вида с обрывом в конце', price: 5990, oldPrice: 5990, discount: 25, count: 123 }, 
                { id: 8, hit: true, brand: 'Бренд', title: 'Полное название товара в несколько строк для вида с обрывом в конце Полное название товара в несколько строк для вида с обрывом в конце', price: 5990, oldPrice: 5990, discount: 25, count: 123 }, 
                { id: 9, hit: true, brand: 'Бренд', title: 'Полное название товара в несколько строк для вида с обрывом в конце Полное название товара в несколько строк для вида с обрывом в конце', price: 5990, oldPrice: 5990, discount: 25, count: 123 }, 
                { id: 10, hit: false, brand: 'Бренд', title: 'Полное название товара в несколько строк для вида с обрывом в конце Полное название товара в несколько строк для вида с обрывом в конце', price: 5990, oldPrice: 5990, discount: 25, count: 123 }, 
                { id: 11, hit: false, brand: 'Бренд', title: 'Полное название товара в несколько строк для вида с обрывом в конце Полное название товара в несколько строк для вида с обрывом в конце', price: 5990, oldPrice: 5990, discount: 25, count: 123 }, 
                { id: 12, hit: false, brand: 'Бренд', title: 'Полное название товара в несколько строк для вида с обрывом в конце Полное название товара в несколько строк для вида с обрывом в конце', price: 5990, oldPrice: 5990, discount: 25, count: 123 }, 
            ]
        }
    }

}
</script>

<style lang="scss" scoped>
    @import '../styles/colors';
    
    .catalog {
        width: 100%;
        display: grid;
        grid-template-columns: 1fr 1fr;
        gap: 24px;
    }

    @media screen and (min-width: 1040px) {
        .catalog {
            grid-template-columns: 1fr 1fr;
        }
    }

    @media screen and (min-width: 1250px) {
        .catalog {
            grid-template-columns: 1fr 1fr 1fr 1fr;
        }
    }

    @media screen and (min-width: 1920px) {
        .catalog {
            grid-template-columns: 1fr 1fr 1fr 1fr 1fr;
        }
    }
</style>