<template lang="html">
  <div class="quote-list">
    <div id="quote-items">
      <quote-item v-for='quote in quotes'
                  :key='quote'
                  :quote='quote'
                  :quotes='quotes'></quote-item>
    </div>
  </div>
</template>

<script>
import Quote from './Item.vue'

export default {
  name: 'QuoteList',
  components: {
    'quote-item': Quote
  },
  props: {
    quotes: Array,
  },
  data: function() {
    return {
      quote:''
    }
  },
  methods: {

  }
}

</script>

<style lang="css" scoped>
.quote-list {
  margin-top: 20px;

}

#quote-items {
  display: flex;
  flex-wrap: wrap;
}
</style>
