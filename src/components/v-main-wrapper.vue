<template>
    <div class="v-main-wrapper">
        <p>{{title}}</p>
        <vCatalog/>
        <vCart/>
    </div>
</template>

<script>
import vCatalog from './v-catalog.vue'
import vCart from './v-cart.vue'
export default {
    name: 'v-main-wrapper',
    components: {
        vCatalog,
        vCart
    },
    props: {},//получает что-то от родителя
    data() {
        return{
            title: 'Main wrapper'
        }
    },
    computed: {},
    methods: {},
    watch: {},
    mounted() {
        console.log('lifehook mounted!')
    }
}
</script>

<style>
.v-main-wrapper{
    max-width: 900px;
    margin: 0 auto;
}
</style>