<template>
    <div class="row product-container">
        <appProduct>
            <img class="card-img-top" src="/src/assets/default.png" alt="Card image cap">
        <div class="card-body">
          <h5 class="card-title">Card title</h5>
          <small>
            <strong>Adet : </strong> 1
          </small>
          <br>
          <small>
            <strong>Fiyat : </strong> 10
          </small>
          <br>
          <small>
            <strong>Tutar : </strong> 10
          </small>
        </div>
        </appProduct>
    </div>
</template>

<script>
import {eventBus} from "../main";
import Product from "./Product.vue"
export default {
    components : {
        appProduct : Product
    },
    data(){
      return{
        productList: [],
      }
    },
    created(){
      eventBus.$on("productAdded",(product)=>{
        this.productList.push(product);
      })
    }
}
</script>