<template>
    <v-app id="inspire">
      <v-navigation-drawer v-model="drawer" width="350">
        <!--  -->
        <LeftSideNav />
        <LogoutButton />
      </v-navigation-drawer>
  
      <v-app-bar class="bg-orange-lighten-1">
        <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
  
        <v-app-bar-title>Dashboard</v-app-bar-title>
      </v-app-bar>
  
      <v-main>
        <v-container>
            <slot />
        </v-container>
      </v-main>
    </v-app>
  </template>
  
  <script setup>
    import { ref } from 'vue'
  
    const drawer = ref(null)
  </script>
  
  <script>
    export default {
      data: () => ({ drawer: null }),
    }
  </script>