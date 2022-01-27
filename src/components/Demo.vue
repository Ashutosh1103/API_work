<template>
  <button v-on:click="updateTitle">Click Here</button>
</template>

<script>
export default {
name:"Demo",
data(){
    return{
        show:false,aclass:"myarray",counter:0
    }
},
methods:{
    updateTitle(){
        this.counter=this.counter+1;
        this.$emit("changeTitle","Parent Title :"+this.counter);
    }
}
}
</script>

<style>

</style>