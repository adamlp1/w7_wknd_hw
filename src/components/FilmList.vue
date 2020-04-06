<template>
<div>
  <h1>Studio Ghibli</h1>  
  <ul>
    <film-selected v-for="(film, index) in films" :film="film" :key="index">{{film.title}}</film-selected>
    </ul>

</div>
</template>

<script>
import FilmSelected from './FilmSelected.vue';

export default {
  name: 'film-list',
  props: ['films'],
  components: {
    "film-selected": FilmSelected
  }
}
</script>

<style scoped>

</style>