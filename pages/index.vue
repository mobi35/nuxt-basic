<template>
  <div class="container">
    <div>
      <div v-for="job in alljobs" :key="job.id">
        <nuxt-link :to="'/jobs/'+ job.id ">
          <JobPostTitle :job="job" v-if="job.company_logo !== null
          && job.title !== null" />
        </nuxt-link>
      </div>

      <h1 class="title">
        buratsssss
      </h1>
      <div class="links">


      </div>
    </div>
  </div>
</template>

<script>
import JobPostTitle from '../components/JobPostTitle'
import axios from 'axios'
export default {
  components:{
    JobPostTitle
  },
  data(){
    allJobs:[]
  },
  head(){
return {
  title: 'Welcome About kantutan',
  meta:[
    {hid:'description',
      name:'description',
      content:'Best kantutanss'}
  ]
}
  },
  async asyncData({params,error}){
    try {
      const {data} = await axios.get(
        'http://localhost:3000/api/positions.json?search=node'
      )
         console.log(data)
      return {alljobs:data}
    } catch (error) {
      console.log(error)

    }
  }
}
</script>
