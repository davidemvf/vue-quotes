<template>
  <div id="app">
    <progressive-bar :quotes='quotes'></progressive-bar>
    <create-quote @quoteCreated='quotes = $event'></create-quote>
    <quote-list :quotes='quotes'></quote-list>
  </div>
</template>

<script>
import ProgressiveBar from './components/ProgressiveBar.vue'
import Quote from './components/Quote.vue'
import QuoteList from './components/QuoteList.vue'

export default {
  name: 'App',
  components: {
    'progressive-bar': ProgressiveBar,
    'create-quote': Quote,
    'quote-list': QuoteList
  },
  data: function() {
    return {
      quotes: []
    }
  }
}
</script>

<style>

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

#app {
  width: 90%;
  height: 700px;
  margin: 0 auto;
}
</style>
