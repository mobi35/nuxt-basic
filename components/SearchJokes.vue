<template>
<form action="" @submit.prevent="OnSubmit">
  <input type="text" v-model="text" placeholder="enter jokes">
  <input type="submit">
</form>
</template>

<script>
export default {
name:'SearchJokes',
data(){
  return {
    text: ''
  }
},methods:{
  OnSubmit(){
    this.$emit('search-text',this.text);
    this.text='';
  }
}
}
</script>

<style>

</style>
