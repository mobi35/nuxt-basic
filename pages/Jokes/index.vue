<template>
  <div>
    <h2>The kantot man</h2>
    <ul class="list-disc flex-wrap">
      <SearchJokes v-on:search-text="searchText"/>
      <Joke  v-for="joke in jokes" :key="joke.id" :id="joke.id" :jokes="joke.joke" />
    </ul>
  </div>
</template>

<script>

import axios from 'axios'
export default {
  data(){
    return{
      jokes:[]
    }
  },async created(){
    const config={
      headers:{
        'Accept' : 'application/json'
      }
    }
  try {
 const res = await axios.get("https://icanhazdadjoke.com/search",config);
 this.jokes = res.data.results;

  } catch (err) {

  }

  },methods:{
    async searchText(text){
const config={
      headers:{
        'Accept' : 'application/json'
      }
    }
  try {
 const res = await axios.get(`https://icanhazdadjoke.com/search?term=${text}`,config);
 this.jokes = res.data.results;

  } catch (err) {

  }
    }
  },
  head(){
return {
  title: 'About kantutans',
  meta:[
    {hid:'descriptionusm',
      name:'descriptionsmsms',
      content:'Best kantutanssmsms'}
  ]
}
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
</style>
