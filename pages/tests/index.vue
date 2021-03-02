<template>
  <h1>Hello Vercel</h1>
</template>

<script>
import axios from 'axios'

export default {
  async asyncData () {
    // let res = {}
    const { data } = await axios.get('https://www.omdbapi.com/?i=tt3896198&apikey=7035c60c')
    console.log(data)
    return {
      res: data
    }
  },
  head () {
    const { Title, Year } = this.res
    return {
      title: `${Title} / ${Year}`
    }
  }
}
</script>
