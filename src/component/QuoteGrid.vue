<template>
    <div class="row">
        <AppQuote v-for="(quote,index) in quotes"  @click.native="deleteQuote(index)">{{ quote }}</AppQuote>
    </div>
</template>

<script>
    import Quote from './Quote.vue';
    export default {
        props:['quotes'],
        components: {
            AppQuote : Quote
        },
        methods:{
         deleteQuote(index){
             this.$emit('deleteQuote',index);
         }   
        }
    }
</script>

<style>

</style>