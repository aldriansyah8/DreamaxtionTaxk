<template>
  <div class="home">

    <div class="container">
      <h1>Products</h1>
        <div class="content" v-for="product in products" :key="product.id" > 

          <CardProduct :product="product"/>

          </div>
      </div>
    </div>
</template>

<script>
// @ is an alias to /src
import CardProduct from '@/components/CardProduct.vue';
import axios from 'axios';

export default {
  name: 'Home',
  components: {
    CardProduct,
  },
  data(){
    return {
      products:[],
      sales:[]
    }
  },
  methods:{
    setProduct(data){
      this.products = data,
      this.sales = data
    }
  },

  mounted() {
    axios
      .get("http://localhost:3000/products")
      .then((response) => this.setProduct(response.data))
      .catch((error) => console.log(error));
  },
}
</script>
