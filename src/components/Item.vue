<template lang="html">
  <div class="item" @click='deleteItem(quote)'>
    <p>"{{ quote }}"</p>
  </div>
</template>

<script>
export default {
  name: 'Item',
  props: {
    quote: String,
    quotes: Array
  },
  methods: {
    deleteItem: function(item) {
      console.log(this.quotes);
      for (var i=0; i<this.quotes.length; i++) {
        if (this.quotes[i] == item) {
          this.quotes.splice(this.quotes[i], 1)
        }
      }
    }
  }
}
</script>

<style lang="css" scoped>
div {
  font-family: 'Arizonia', cursive;
  color: #6e6e6e;
  width: 222px;
  padding: 50px 7px 50px 7px;
  background-color: white;
  margin: 0 10px 10px 10px;
  text-align: center;
  cursor: pointer;
  border: 2px solid rgb(234,233,234);
  border-radius: 4px;
  box-shadow: 5px 5px 5px #dedede;
  word-break: break-all;
}

.item:hover {
  background-color: #ffe2e2;
}

</style>
