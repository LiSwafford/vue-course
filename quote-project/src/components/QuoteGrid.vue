<template>
  <div class="row">
    <Quote 
    v-for="(quote, i) in quotes" 
    :key="i"
    @click.native="deleteQuote(i)">{{ quote }}</Quote>
  </div>
</template>

<script>
  import Quote from './Quote.vue';
  export default {
    props:['quotes'],
    methods: {
      deleteQuote(i) {
        this.$emit('quoteDeleted', i);
      }
    },
    components: {
      Quote
    }
  }
</script>

<style>

</style>
