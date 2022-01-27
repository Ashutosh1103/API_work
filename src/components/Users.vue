<template>
  <div>
      <h2>Users Details</h2>
      <table class="table">
          <tr>
                <th>S.no</th>
                <th>Name</th>
                <th>Username</th>
                <th>Email</th>
                <th>Website</th>
                <th>Phone</th>          
          </tr>
          <tr v-for="(user,index) in userData" :key="user.id">
              <td>{{index+1}}</td>
              <td>{{user.name}}</td>
              <td>{{user.username}}</td>
              <td>{{user.email}}</td>
              <td>{{user.website}}</td>
              <td>{{user.phone}}</td>
          </tr>
      </table>
      <hr>
  </div>
</template>

<script>
import Vue from 'vue';
import VueAxios from 'vue-axios';
import axios from 'axios';
Vue.use(VueAxios,axios);
export default {
    name:"Users",
    data(){
        return{userData:undefined}
    },
    mounted(){
        const URL="https://jsonplaceholder.typicode.com/users";
        Vue.axios.get(URL)
        .then(res=>{
            console.log(res.data);
            this.userData=res.data;
        })
    }

}
</script>

<style>

</style>