<template>
    <div class="v-catalog-item">
        <img v-bind:src=" require('../assets/images/' + product_data.image) " alt="img" class="v-catalog-item__image">
        <p class="v-catalog-item__name">{{ product_data.name }}</p>
        <p class="v-catalog-item__price">Price: {{ product_data.price }}$</p>
        <button class="v-catalog-item__add-to-cart-bnt btn" @click="sendDataToParent">Add to cart</button>
    </div>
</template>

<script>
export default {
    name: 'v-catalog-item',
    components: {},
    props: {//получает что-то от родителя
        product_data: {
            type: Object,
            default() {
                return {}
            }
        }
    },
    data() {
        return{
            
        }
    },
    computed: {},
    methods: {
        sendDataToParent(){
            this.$emit('sendArticle', this.product_data.article)//теперь sendArticle можно использовать в родителе
            //отправляет родителю такой же метод, только с другим названием в данном случае + аргумент(автоматически передается в аргумент data локального метода в родителе)
        }
    },
    watch: {},
    mounted() {}//после выполнения кода вроде выполняется этот код
}
</script>

<style lang="scss">
    .v-catalog-item{
        flex-basis: 25%;
        box-shadow: 0 0 8px 0 #e0e0e0;
        padding: $padding*2;
        margin-bottom: $margin*2;
        &__image{
            width: 200px;
            height: 250px;
        }
    }
</style>