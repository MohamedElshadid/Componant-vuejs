<template>
    <div class="row">
        <AppQuote v-for="quote in quotes">{{ quote }} </AppQuote>
    </div>
</template>

<script>
    import Quote from './Quote.vue';
    export default {
        props:['quotes'],
        components: {
            AppQuote : Quote
        }
    }
</script>

<style>

</style>