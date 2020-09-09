<template>
  <header class="header">
    <h1 class="title">Dad Jokes</h1>
    <ul>
      <li>
         <nuxt-link class="h-6 text-red-700" to="/"> About page</nuxt-link>
        <nuxt-link to="/about"> About page</nuxt-link>
        <nuxt-link to="/Jokes/"> dad page</nuxt-link>
      </li>
    </ul>
  </header>
</template>

<script>
export default {
  name: 'AppHeader'

}
</script>

<style>

</style>
