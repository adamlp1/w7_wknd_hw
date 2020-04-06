<template>
  <div>
<h3 v-on:click="handleClick"> {{film.title}}</h3>
  </div>
</template>

<script>
import { eventBus } from '../main.js';

export default {
  name: 'film-selected',
  props: ['film'],
  methods: {
    handleClick(){
      eventBus.$emit( 'film-selected', this.film )
    },
  }

}
</script>

<style scoped>

</style>