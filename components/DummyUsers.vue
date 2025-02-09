<!-- DummyUsers.vue -->
<template>
    <!-- ERROR (item-value="username") -->
    <v-data-table :items="users"> 
      <template v-slot:[`item.username`]="{ item }">
        <span>{{ item.username }}</span>
      </template>
      <template v-slot:[`item.role`]="{ item }">
        <span>{{ item.role }}</span>
      </template>
    </v-data-table>
  </template>
  
<script setup>
//   vue 2 approach
//   export default {
//     props: {
//       users: Array
//     }
//   }

const props = defineProps({
    users: {
    type: Array,
    required: true
    }
})
</script>
  