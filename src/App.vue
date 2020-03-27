<template>
  <div id="app">
    <progressive-bar :quotes='quotes'></progressive-bar>
    <create-quote @quoteCreated='quotes = $event'></create-quote>
    <quote-list :quotes='quotes'></quote-list>
    <div class="footer">
      <p><strong>Info: click on a Quote to delete it</strong></p>
    </div>
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

.footer {
  width: 100%;
  text-align: center;
  background-color: rgb(216,237,247);
}

.footer p{
  padding: 15px 0;
  color: rgb(56,53,66);
  font-family: Arial;
}

</style>
