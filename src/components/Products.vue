<template>
  <div>
      <h2>Products</h2>
      <div class="row">
          <div class="col-md-4" v-for="pro of proData" :key="pro.id">
              <div class="card" style="width: 18rem;">
                <img :src="pro.image" width="200" height="150" class="card-img-top" alt="...">
                <div class="card-body">
                    <h5 class="card-title">{{pro.pname}}</h5>
                    <p class="card-text">
                        Price: <b>{{pro.price}}</b><br/>
                        quantity: <b>{{pro.quantity}}</b><br/>
                    </p>
                    <a href="javascript:void(0)" class="btn btn-primary">Add To Card</a>
                    <a href="javascript:void(0)" class="btn btn-primary" v-on:click="delPro(pro.id)">Delete</a>
                </div>
                </div>
          </div>
      </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
name:"Products",
data(){
    return{
        proData:undefined
    }
},
methods:{
     delPro(id){
           const URL="http://localhost:300/products/";
          if(confirm("Do u want to delete it ?")){
              axios.delete(`${URL}${id}`)
              .then(res=>{
                  if(res){
                       axios.get(URL)
                       .then(res=>{
                         this.proData=res.data;
                     })
                  }
              })
          }
      }
},
mounted(){
    const URL="http://localhost:300/products";
    axios.get(URL)
    .then(res=>{
        console.log(res.data)
        this.proData=res.data;
    })
},

}
</script>

<style>

</style>