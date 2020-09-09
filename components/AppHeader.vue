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
    <ul>
      <li v-for="(item,index) in items" :key="index">

        <nuxt-link :to="item.to">
          <p>{{ item.title}}</p>
        </nuxt-link>

      </li>
    </ul>
  </header>
</template>

<script>
export default {
  name: 'AppHeader',
  data: () => ({

    items:[
      {title: 'Home',to: {name: 'index'} },
       {title: 'About',to: {name: 'about'} },
    ]

  })

}
</script>

<style>

</style>
