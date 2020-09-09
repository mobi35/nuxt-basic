<template>
<div>
  <img :src="job.company_logo" alt="">
  <h1>
    {{job.title}}
  </h1>
  <p>Views : {{views}}</p>
</div>
</template>

<script>
export default {
  name:'JobPost',
  props: {
   job:{
     type: Object,
     required: true,
     default: () => {}
   },  views:{
     type: Number,
     required: false,
     default: () => 0
   }
 }
}
</script>

<style>

</style>
