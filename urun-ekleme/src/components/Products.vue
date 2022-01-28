<template>
    <div class="row product-container">

      <div class="col-md-2 card">
          
        <img class="card-img-top" :src="product.selectedImage" :alt="product.title">
        <div class="card-body">
          <h5 class="card-title">{{product.title}} </h5>
          <small>
            <strong>Adet : </strong> {{product.count}}
          </small>
          <br>
          <small>
            <strong>Fiyat : </strong> {{product.price}}
          </small>
          <br>
          <small>
            <strong>Tutar : </strong> {{product.totalPrice}}
          </small>
        </div>
      </div>
    </div>
</template>
<script>
    import {eventBus} from "../main";

    export default {
        data(){
            return{
                productList: [],
            }
        },
        created(){
            eventBus.$on("productAdded",(product) =>{
                this.productList.push(product);
            });
        } 
    }
</script>
