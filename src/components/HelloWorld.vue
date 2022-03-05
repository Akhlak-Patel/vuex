<template>
  <div>
    <AddProduct/>
    <h2>Hello from vuex</h2>
    <ul>
      <li v-for="product in allProducts" :key="product.id">{{product.name}} | {{product.price}}
        <button @click="deleteProduct(product.id)">Delete</button>
      </li>
      
    </ul>
    
  </div>
</template>

<script>
import {mapGetters,mapActions} from "vuex"
import AddProduct from './AddProduct.vue'
export default {
  name: 'HelloWorld',
  components:{AddProduct},
  computed:mapGetters(["allProducts"]),
  methods:{
    ...mapActions(["getProducts","deleteProduct"]),
  },
  created(){
    this.getProducts()
  }
}
</script>
