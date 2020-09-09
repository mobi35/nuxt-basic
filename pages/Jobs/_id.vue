<template>
  <div>
    <JobPost :views="views('/jobs/'+ currentJobPost.id)"  :job="currentJobPost"/>
  </div>
</template>

<script>
import JobPost from '../../components/JobPost'
import axios from 'axios'
import { mapGetters } from 'vuex'
export default {
components:{
  JobPost
},data(){
  return {
    currentJobPost:{}
  }
} ,head(){
return {
  title: 'About the Job',
  meta:[
    {hid:'description',
      name:'description',
      content:'Best kantutanss'}
  ]
    }
  },
  methods:{
    getMetaTitle(){
      this.currentJobPost.title + ' at ' + this.currentJobPost.company
    },
  },computed: mapGetters({
    views: 'getViews'
  }),
  async asyncData({params,error}){
    try {
      const {data} = await axios.get(
        `http://localhost:3000/api/positions/${params.id}.json`
      )

      return {currentJobPost:data}
    } catch (error) {


    }
  },middleware:'views'
}
</script>

<style>

</style>
