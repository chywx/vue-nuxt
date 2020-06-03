<template>
  <div>
    <div v-for="sport of sportList">
      <h1>{{sport.name}}</h1>
    </div>
  </div>
</template>

<script>
  import axios from 'axios'

  export default {
    name: 'sport',
    data () {
      return {
        sportList: []
      }
    },
    created () {
      this.getData()
    },
    methods: {
      async getData () {
        let { data } = await axios({
          method: 'get',
          url: `http://117.78.10.187:9009/api/bet/sport/list`
        })
        this.sportList = data.data
      }
    },
  }
</script>

<style scoped>

</style>
