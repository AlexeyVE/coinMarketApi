<template>
  <section class="container">
    <div class="row">
      <div class="col-4" v-for="coin in coinsData">
        {{coin.name}}
      </div>
    </div>
  </section>
</template>

<script>
import axios from 'axios'
export default {
  name: 'mainPage',
  data () {
    return {
      coinsData:[]
    }
  },
  methods: {
    getData () {
      axios.get('https://api.coinmarketcap.com/v1/ticker/?limit=100')
      .then(res => {
        this.coinsData = res.data
        console.log(this.coinsData)
      })            
    }
  },
  created () {
    this.getData()
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>

</style>
