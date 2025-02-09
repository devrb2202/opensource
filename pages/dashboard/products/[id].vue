<template>
    <h1>Details Page</h1>
    <h1>Item ID : {{ id }}</h1>
    <v-btn color="primary" to="/dashboard/products/view">Back to Products</v-btn>
</template>

<script setup>
definePageMeta({
    layout: 'dashboard'
})

const route = useRoute()
const id = ref(route.params.id)



</script>

