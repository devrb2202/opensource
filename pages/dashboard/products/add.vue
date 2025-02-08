<template>
    <div>
        <h1>Add Product Page</h1>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Exercitationem, qui.
    </div>
</template>

<script setup>

definePageMeta({
    layout: 'dashboard'
})
</script>


<!-- 
 <template>
    <div>
      <h1>Add New Product</h1>
      
      <form @submit.prevent="addProduct">
        <label for="title">Title:</label>
        <input type="text" v-model="newProduct.title" id="title" required />
  
        <label for="price">Price:</label>
        <input type="number" v-model="newProduct.price" id="price" required />
  
        <label for="description">Description:</label>
        <input type="text" v-model="newProduct.description" id="description" required />
  
        <label for="image">Image URL:</label>
        <input type="url" v-model="newProduct.image" id="image" required />
  
        <label for="category">Category:</label>
        <input type="text" v-model="newProduct.category" id="category" required />
  
        <button type="submit">Add Product</button>
      </form>
      
      <div v-if="response">
        <h2>Response:</h2>
        <pre>{{ response }}</pre>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue'
  
  const newProduct = ref({
    title: '',
    price: '',
    description: '',
    image: '',
    category: ''
  })
  
  const response = ref(null)
  
  const addProduct = async () => {
    try {
      const res = await fetch('https://fakestoreapi.com/products', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
        },
        body: JSON.stringify(newProduct.value),
      })
  
      const json = await res.json()
      response.value = json
      console.log(json)
    } catch (error) {
      console.error('Error:', error)
      response.value = { error: 'Failed to add product' }
    }
  }

  definePageMeta({
    layout: 'dashboard'
})
  </script>
   -->