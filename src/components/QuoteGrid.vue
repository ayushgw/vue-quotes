<template>
    <div class="row">
        <app-quote v-for="(quote, index) in quotes" :key="'quote' + index" @click.native="deleteQuote(index)">
            {{quote}}
        </app-quote>
    </div>
</template>

<script>
import Quote from './Quote.vue';

export default {
    props: ['quotes'],
    components: {
        appQuote: Quote
    },
    methods: {
        deleteQuote(i) {
            this.quotes.splice(i, 1);
        }
    }
}
</script>

<style>

</style>
