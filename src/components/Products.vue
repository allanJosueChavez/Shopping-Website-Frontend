<template>
    <div id="products">Hola
     <div v-for="(product, index) in products" :key="product.id">
      <p>The new product is: {{product.name}}</p>
     </div>
    </div>
   </template>

<script>

export default {  
 name: 'Products',
 data() {
  return {
    products: []
  }
 },
 created() {
  axios.get('localhost:3000/products') 
  .then(response => {
   this.products = response.data
  })
 .catch(e => {
  this.error.push(e)
  })
 },
}
</script>