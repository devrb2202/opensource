<template>
    <div>
        <h1>View Product Page</h1>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Exercitationem, qui.
        <v-container>
            <v-row no-gutters>

                <v-col cols="12" sm="6" md="4" lg="3" v-for="p in products" :key="p.id">
                    <v-card class="ma-4">
                        <ProductList :product="p"/>
                    </v-card> 
                </v-col>   
            </v-row>
        </v-container>
    </div>
</template>

<script setup>
import ProductList from '~/components/ProductList.vue';



definePageMeta({
    layout: 'dashboard'
})


const { data: products } = await useFetch('https://fakestoreapi.com/products') 


</script>
