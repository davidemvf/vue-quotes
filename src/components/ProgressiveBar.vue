<template lang="html">
  <div class='header'>
    <div class="bar">
      <h1><strong>Quotes Added</strong></h1>
      <img alt="Vue logo" :src="require('@/assets/logo.png')"/>
    </div>
      <div class="grey-bar">
        <div class="blue-bar" :style="{width: (quotes.length/capacity) * 100 + '%' , transition: 1 + 's'}">
          <p>{{ quotes.length === 0 ? '' : (quotes.length/capacity) * 100 + '%' }}</p>
        </div>
      </div>
  </div>

</template>

<script>


export default {
  name: 'ProgressiveBar',
  props: {
    quotes: Array
  },
  data: function() {
    return {
      capacity: 10,
      quoteNumbers: this.quotes.length
    }
  },
}
</script>

<style lang="css" scoped>
  .header {
    width: 100%;
    height: 120px;
  }

  .bar {
    padding-top: 50px;
    display: flex;
    align-items: center;
  }

  .header h1 {
    color: rgb(56,53,66);
    font-family: Arial, Helvetica, sans-serif;
    font-size: 25px;
    display: inline;
  }

  .header img {
    height: 30px;
    margin-left: 10px;
  }

  .grey-bar {
    width: 100%;
    height: 15px;
    background-color: rgb(245,244,246);
    border-radius: 6px;
    margin-top: 10px;
  }

  .blue-bar {
    color: rgb(245,244,246);
    height: 100%;
    background-color: rgb(52,122,185);
    border-radius: 6px;
    text-align: center;

  }
</style>
