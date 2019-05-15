<template>
  <div class="fav" id="fav">
    <h1>Bitcoin Price Index</h1>
    <section v-if="errored">
      <p>We're sorry, we're not able to retrieve this information at the moment, please try back later</p>
    </section>
    <section v-else>
      <div v-if="loading">loading...</div>
    
    <div
      v-else
      v-for="currency in info" :key="currency.id"
      class="currency"
    >
      {{ currency.description }}:
      <span class="lighten">
        <span v-html="currency.symbol"></span>{{ currency.rate_float | currencydecimal }}
      </span>
    </div>
    </section>
  </div>
</template>

<script>
import axios from 'axios'
import { error } from 'util';

export default {
  data () {
    return {
      info: null,
      loading: true,
      errored: false
    }
  },
  filters: {
    currencydecimal (value) {
      return value.toFixed(2)
    }
  },
  mounted () {
    axios
      .get('https://api.coindesk.com/v1/bpi/currentprice.json')
      .then(response => {
        this.info = response.data.bpi
      })
      .catch(error => {
        console.log(error)
        this.errored = true
      })
      .finally(() => this.loading = false)
  }
  
  
}
</script>
<style>
.fav {
  background-color: black;
  width: 60%;
  margin: 0 auto;
  border:1px solid #B3BFB8;
  border-radius: 15px;
}
h1 {
  color: white;
  
}
.currency {
  color: #B3BFB8
}
</style>

