<!-- UsersManagement.vue -->

<template>
    <div>
      <h1>Users Management Page</h1>
      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Amet, iusto.

      <v-container>
        <v-row>
            <v-card>
                <v-text-field label="Username" v-model="username"></v-text-field>
                <v-text-field label="Password" v-model="password"></v-text-field>
                <v-text-field label="Role" v-model="roles"></v-text-field>
                <v-btn @click="addUser">add</v-btn>
            </v-card>
        </v-row>
      </v-container>
      <v-container>
        <v-row align-content-sm="center">
          <v-col cols="12">
            <DummyUsers :users="users" />
          </v-col>
        </v-row>
      </v-container>
    </div>
  </template>

<script setup>
import { ref } from 'vue'
//   import DummyUsers from '~/components/DummyUsers.vue'

const username = ref('')
const password = ref('')
const roles = ref('')
const users = ref([])



function addUser() {
    if(username.value.trim() && password.value.trim() && roles.value.trim()){
        users.value.push({
            username: username.value,
            password: password.value,
            roles: roles.value
        })
        username.value = ''
        password.value = ''
        roles.value = ''

    alert('Added New User!')
    }

    else{
        alert('Error')
    }
}

definePageMeta({
    layout: 'dashboard'
})
</script>
  