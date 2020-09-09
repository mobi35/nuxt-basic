<template>
<div>
  <h2>{{job.title}}</h2>
  <img style="height:200px" :src="job.company_logo" />

</div>
</template>

<script>
export default {
 name:'JobPostTitle',
 props: {
   job:{
     type: Object,
     required: true,
     default: () => {}
   }
 },
 created(){

 }
}
</script>

<style>

</style>
