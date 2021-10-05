<template>
  
    <div class="in-content">
      <span v-if="product.stock < 10">
      <p class="number color1">{{product.stock}}</p>
      </span>
      <span v-else>
      <p class="number color2">{{product.stock}}</p>
      </span>

        <div class="desc-content">
          <p class="name-content">{{product.name}}</p>
            <div class="description">
              <p class="left">Total Sold</p>
              <p class="right default">{{product.stock}}</p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
name:"CardProduct",
props:['product']
}
</script>

<style>

</style>