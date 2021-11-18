<template>
    <div class="v-catalog">
        <vCatalogItem
            v-for="product in products"
            :key="product.article"
            v-bind:product_data="product"
            @sendArticle="showChildArticleConsole($event)"
        />
    </div>
</template>

<script>
//:key - сюда должно передаваться любое УНИКАЛЬНОЕ значение, иначе не будет работать
//:product_data новый объект product передается в props ребенка при каждой новой итерации

import vCatalogItem from './v-catalog-item.vue'
export default {
    name: 'v-catalog',
    components: {
        vCatalogItem
    },
    props: {},//получает что-то от родителя
    data() {
        return{
            products: [
                {
                    image: "1.jpg",
                    name: "T-shirt",
                    price: 100,
                    article: "T1",
                    available: true
                },
                {
                    image: "2.jpg",
                    name: "T-shirt black",
                    price: 300,
                    article: "T2",
                    available: false
                },
                {
                image: "3.jpg",
                name: "T-shirt",
                price: 100,
                article: "T3",
                available: true
                },
                {
                image: "4.jpg",
                name: "T-shirt",
                price: 100,
                article: "T4",
                available: true
                },
                {
                image: "5.jpg",
                name: "T-shirt",
                price: 100,
                article: "T5",
                available: true
                },
                {
                image: "6.jpg",
                name: "Boots",
                price: 500,
                article: "IL-01",
                available: false
                },
                {
                image: "7.jpg",
                name: "Jacket",
                price: 2000,
                article: "T1-f",
                available: true
                }
            ]
        }
    },
    computed: {},
    methods: {
        showChildArticleConsole(data){
            console.log(data);
        }
    },
    watch: {},
    mounted() {}
}
</script>

<style lang="scss">
    .v-catalog{
        
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            align-items: center;
        
    }
</style>