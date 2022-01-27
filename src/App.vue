<template>
  <div id="app">
    <!-- <Regis/> -->
     
     <!-- <h2>{{title}}</h2>
       <Demo v-on:changeTitle="xyz($event)"/> -->
<!-- <Users/>
       <Post/> -->

       <Products/>
       
  </div>
</template>

<script>
//import Regis from './components/Regis.vue'
//import Demo from './components/Demo.vue'
// import Post  from './components/Posts.vue'
//import Users  from './components/Users.vue'
import Products  from './components/Products.vue'
export default {
  name: 'App',
  components:{
    // Regis,
   // Demo,
  //  Post,
  //  Users,
  Products
  },
//   data(){
//     return{
//         title:0
//     }
// },
//   methods:{
//     xyz(val){
//       this.title=val;
//     }
//   }
        
    };
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
