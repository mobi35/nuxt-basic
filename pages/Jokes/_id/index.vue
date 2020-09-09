<template>
  <div>
    <nuxt-link to="/jokes"> Back to Jokes</nuxt-link>

   <h2>  {{ jokes }} </h2>
   <small>JOKE IDL {{ $route.params.id}}</small>
  </div>
</template>

<script>
import axios from 'axios'
export default {
data(){
  return {
    jokes:{

    }
  }
},
async created(){
    const config={
      headers:{
        'Accept' : 'application/json'
      }
    }
  try {
 const res = await axios.get(`https://icanhazdadjoke.com/j/${this.$route.params.id}`,config);
 this.jokes = res.data.joke;

  } catch (err) {

  }

  },head(){
return {
  title: this.jokes,
  meta:[
    {hid:'descriptionusm',
      name:'descriptionsmsms',
      content:'Best kantutanssmsms'}
  ]
}
  }
};
</script>

<style>

</style>
