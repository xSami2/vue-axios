<script setup>
let props = defineProps({
  title : String ,
  description : String ,
  price : Number ,
  discountPercentage : Number,
  stock : Number,
  brand : String ,
  images : String
})

</script>

<template>
  <div class="card" style="width: 18rem;">
    <img :src="props.images" class="card-img-top" alt="...">
    <div class="card-body">
      <h5 class="card-title">{{props.title}}</h5>
      <p class="card-text">{{props.description}}</p>
      <div class="d-flex">
        <h6> Price : {{props.price}}</h6> <h6 class="mx-3"> Discount :<span class="text-danger">{{props.discountPercentage}}%</span>
      </h6>
      </div>
      <h5 class="mt-3" v-if="props.stock !== 0"> in Stock</h5>
      <h5 class="mt-3 text-danger" v-if="props.stock === 0"> Out of Stock</h5>
      <a href="#" class="btn btn-success">Add to Basket</a>

    </div>
  </div>
</template>
