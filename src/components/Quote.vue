<template lang="html">
  <div class="quote-section">
    <div class="create-quote">
      <p><strong>Quote</strong></p>
      <textarea
        placeholder="Inserisci una citazione..."
        name="name"
        rows="8"
        cols="80"
        v-model='quote'>
      </textarea>
      <button
        type="button"
        name="button"
        @click.enter= 'pushQuote()'>
        <strong>Add Quote</strong></button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Quote',
  data: function() {
    return {
      quote: '',
      quotes: []
    }
  },
  methods: {
    pushQuote: function() {
      if (this.quotes.length < 10 && this.quote != '') {
      this.quotes.push(this.quote)
      // console.log(this.quotes)
      this.quote = '';
      // passo l'array ai componenti fratelli tramite il padre (App)
      this.$emit('quoteCreated', this.quotes)
    } else {
      alert('Raggiunto limite massimo o campo vuoto.')
    }
    }
  }
}
</script>

<style lang="css" scoped>

.create-quote {
  width: 50%;
  margin: 20px auto;
}

p {
  color: rgb(56,53,66);
  font-family: Arial, Helvetica, sans-serif;
  font-size: 20px;
  margin-bottom: 3px
}

textarea {
  font-family: Arial, Helvetica, sans-serif;
  width: 100%;
  height: 100px;
  padding: 10px;
  border-radius: 6px;
}

button {
  color: white;
  font-family: Arial, Helvetica, sans-serif;
  font-size: 16px;
  display: block;
  height: 40px;
  width: 100px;
  background-color: rgb(52,122,185);
  margin: 10px auto;
  border: none;
  border-radius: 6px;
  cursor: pointer;
}
</style>
