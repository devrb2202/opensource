
<template>

    <v-card class="pa-4 align-center">
        <v-img
        :src="product.image"
        width="100%" 
        height="200"
        class="mb-4"
        >
        </v-img>
        <v-divider></v-divider>
        <v-card-text class="text-truncate">{{ product.title }}</v-card-text>
        <v-card-text class="text-truncate">Category : {{ product.category }}</v-card-text>
        <v-spacer></v-spacer>
        <v-card-text class="d-flex justify-space-between align-center">
            <span>Price : ${{ product.price }}</span>
            <NuxtLink :to="`/dashboard/products/${product.id}`">
                <v-btn color="primary">View Details</v-btn>
            </NuxtLink>
                   
        </v-card-text>
     
    </v-card>
   
   
</template>

<script setup>
const { product } = defineProps(['product'])   


</script>
