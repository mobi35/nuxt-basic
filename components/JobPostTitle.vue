<template>
<div>
  <h2>{{job.title}}</h2>
  <img style="height:200px" :src="job.company_logo" />
  <p>
    Views: {{views}}
  </p>
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
   },  views:{
     type: Number,
     required: false,
     default: () => 0
   }
 },
 created(){

 }
}
</script>

<style>

</style>
