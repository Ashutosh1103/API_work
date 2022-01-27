<template>
<div>
  <h2>Latest Posts</h2>
  <div v-for="post in postData" :key="post.id">
      <h4>{{post.title}}</h4>
      <article>{{post.body}}</article>
  </div>
  <hr/>
</div>
</template>

<script>
export default {
name:"Posts",
data(){
    return{postData:undefined}
},
mounted(){
    const URL="https://jsonplaceholder.typicode.com/posts";
    fetch(URL)
    .then(res=>res.json())
    .then(data=>{
        console.log(data)
        this.postData=data;
    })
}
}
</script>

<style>

</style>