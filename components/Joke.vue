<template>
<nuxt-link :to="'/jokes/' + id">

<div>
  <p>{{ jokes}}</p>
</div>

</nuxt-link>
</template>

<script>
export default {
name:'Joke',
props:['jokes','id']
}
</script>

<style>

</style>
