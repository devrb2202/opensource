<template>
    <v-container class="d-flex justify-center align-center rounded-lg">
        <v-card width="500">

            <v-card-title class="text-h1 font-weight-bold text-center">{{ error.statusCode }}</v-card-title>
            <v-card-text class="text-h6 text-center">Please try again later</v-card-text>
            <v-card-text class="text-h6 text-center">{{ error.message }}</v-card-text>
            <v-container class="d-flex justify-center">
                <v-btn text="back to home" color="green" @click="handleClearError"></v-btn>
            </v-container>
        </v-card>
    </v-container>
</template>

<script setup>

defineProps(['error'])

//clear error when click the back button on browser
const handleClearError = () => clearError({ redirect: '/'})




</script>
