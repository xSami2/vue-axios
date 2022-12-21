<script setup>
import {inject, onMounted} from 'vue'
import Item from "@/components/Item.vue";

const axios = inject('axios')

let API_Responses = Object ;

onMounted( () => {

  axios.get('https://dummyjson.com/products').then(  (result) => { API_Responses = result.data.products }  )
})

</script>

<template>

  <header class="bg-dark ">
    <div class="d-flex justify-content-between">
      <div class="d-flex mt-2">
       <i class="fa-solid fa-phone text-white mt-2"> </i>
        <h6 class="text-white fs-5 px-2 mt-1 ">+966 53 113 1327</h6>
      </div>


        <div class="text-dark d-flex mt-2">
             <a href="#" class="nav-link d-flex">
            <i class="fa-regular fa-user text-white mt-2"></i>
            <h6 class="text-white fs-5 px-2 mt-1 ">My Account</h6>

             </a>
        </div>
    </div>
 </header>

<div class="container-fluid bg-light border-bottom p-1 ">

  <div class="row ">


  <div class="col mt-2">
        <h3>World of Technology</h3>
  </div>

  <div class="col text-center  d-flex p-1" >
    <div class="btn-group" role="group" aria-label="Basic checkbox toggle button group">

      <div class="btn-group">
        <button type="button" class="btn btn-success dropdown-toggle" data-bs-toggle="dropdown" aria-expanded="false">
          Category
        </button>
        <ul class="dropdown-menu">
          <li><a class="dropdown-item" href="#">SmartPhone</a></li>
          <li><a class="dropdown-item" href="#">SmartWatch</a></li>
          <li><a class="dropdown-item" href="#">Laptop</a></li>

        </ul>
      </div>

      <input class="form-control" placeholder="What product in mind?">
     <button class="btn btn-primary">Search</button>
    </div>
  </div>

  <div class="col text-end mt-2">
    <span class="align-middle">
          <img  class="rounded-circle mr-2" style="width: 40px ; height: 40px"  src="https://mir-s3-cdn-cf.behance.net/project_modules/max_1200/4dbe2e83261589.5d371e45eed23.png" alt="">

    </span>
  </div>

  </div>
</div>

  <div class="container-fluid bg-success bg-gradient">

    <div class="row text-dark">

      <div class="col-1 text-center">

            <a href="#" class="nav-link">
              <h4>Home</h4>
            </a>
      </div>

      <div class="col-1 ">

        <a href="#" class="nav-link">
          <h4>Hot Deals</h4>
        </a>
      </div>

      <div class="col-2 ">

        <a href="#" class="nav-link">
          <h4>New Product</h4>
        </a>
      </div>


    </div>

  </div>
  <img style="width: 2000px; height: 400px" src="https://cdn.pixabay.com/photo/2013/12/28/01/55/hang-tags-234566_960_720.jpg" alt="">
<hr/>

  <div class="container-fluid mb-4">

    <div class="row">

      <div class="col-3 text-center">
        <h4>Our Product</h4>
      </div>

      <div class="col-9">

      </div>


    </div>

  </div>


 <div class="d-flex container justify-content-between ">
   <div v-for="(value , index ) in API_Responses">

     <div class="d-flex">
       <Item
           :title="API_Responses[index].title"
           :description="API_Responses[index].description"
           :price="API_Responses[index].price"
           :discount-percentage="API_Responses[index].discountPercentage"
           :stock="API_Responses[index].stock"
           :images="API_Responses[index].images[0]"
       />

     </div>
   </div>
 </div>
</template>



