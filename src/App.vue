<template>
  <div class="container">
    <app-header :maxQuotes="maxQuotes" :quoteCount="quotes.length"></app-header>
    <app-new-quote @quoteAdded="newQuote"></app-new-quote>
    <app-quote-grid :quotes="quotes"></app-quote-grid>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">Info: Click on a quote to delete it!</div>
      </div>
    </div>
  </div>
</template>

<script>
import QuoteGrid from "./components/QuoteGrid.vue";
import NewQuote from "./components/NewQuote.vue";
import AppHeader from "./components/Header.vue";

export default {
  data() {
    return {
      maxQuotes: 10,
      quotes: ["Just a quote"]
    };
  },
  components: {
    appQuoteGrid: QuoteGrid,
    appNewQuote: NewQuote,
    appHeader: AppHeader
  },
  methods: {
    newQuote(quote) {
      if (this.quotes.length >= this.maxQuotes) {
        return alert(
          "Maximum quotes registerted! Please delete quotes to add new ones."
        );
      } else if (quote.length < 1) {
        return alert(
          "Please enter a quote to add."
        );
      }
      this.quotes.push(quote);
    }
  }
};
</script>

<style>
</style>
