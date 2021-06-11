<template>
  <div id="app">
    <h1>Preços do Bitcoin</h1>
    <div v-for="currency in info"
      class="currency" :key="currency.symbol">
      {{ currency.description }}:
      <span class="lighten">
        <span v-html="currency.symbol"></span>{{ currency.rate_float | currencydecimal }}
      </span>
    </div>
  </div>
</template>

<script>
const axios = require('axios').default
export default {
  el: "#app",
  data() {
    return {
      info: null,
    };
  },
  mounted() {
    axios
      .get("https://api.coindesk.com/v1/bpi/currentprice.json")
      .then(response => (this.info = response.data.bpi))
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  div {
    display: block;
    text-align: center;
  }
  #app {
    margin-top: 20px;
    width: 300px;
    padding: 0 40px 40px;
    background: #2F242C;
    border-radius: 5px;
    color: #B3BFB8;
  }

</style>
