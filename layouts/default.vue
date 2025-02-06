<template>
    <v-app>
        <v-app-bar class="bg-orange-lighten-1">
            <v-toolbar-title>
                <v-icon>mdi-cart</v-icon>Shop Manigga
            </v-toolbar-title>
            <v-spacer></v-spacer>
            <v-btn text to="/">Home</v-btn>
            <LoginRegisterDropDown />
            
            <!-- <v-btn text to="/login">login</v-btn> -->
        </v-app-bar>
        <v-main>
            <!-- <v-container class="d-flex justify-center align-center w-75">
                <slot />
            </v-container> -->
            <slot />
            
        </v-main>
    </v-app>
    
</template>

<script>

</script>

