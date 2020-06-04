<template>
  <div class="container">
    <AppHeader :quoteCount="quotes.length" :maxQuotes="maxQuotes"></AppHeader>
    <AppNewQuote @quotedAdded="NewQuote"></AppNewQuote>
    <AppQuoteGrid :quotes="quotes" @deleteQuote="DeleteQuote"></AppQuoteGrid>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">Info: Click pn a Quote to delete it! </div>
      </div>
    </div>
  </div>
</template>

<script>

import QuoteGrid from './component/QuoteGrid';
import NewQuote from './component/NewQuote';
import Header from './component/Header';
  export default{
    data:function(){
      return {
        quotes: ['Just a Quote to start'],
        maxQuotes : 10
      }
    },
    components:{
      AppQuoteGrid : QuoteGrid,
      AppNewQuote:NewQuote,
      AppHeader:Header
    },
    methods:{
      NewQuote(event){
        if(this.quotes.length >= this.maxQuotes){
          return alert('Please delete Quote first!');
        }
        this.quotes.push(event);
      },
      DeleteQuote(index){
        this.quotes.splice(index,1);
      }
    }
  }
</script>

<style>

</style>
