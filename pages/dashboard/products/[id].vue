<template>
    Lorem ipsum dolor sit amet consectetur adipisicing elit. Quaerat, quasi?
    {{ id }}
</template>

<script setup>
definePageMeta({
    layout: 'dashboard'
})

const route = useRoute()
const id = ref(route.params.id)



</script>

