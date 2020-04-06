<template>
  <div>
  <film-list :films='films'></film-list>
  <film-detail :film='selectedFilm'></film-detail>
  </div>
  
</template>

<script>

import FilmList from './components/FilmList.vue'
import FilmDetail from './components/FilmDetail.vue'
import { eventBus } from './main'

export default {
  data(){
    return {
      films: [],
      selectedFilm: null
    }
  },
  components: {
    'film-list': FilmList,
    'film-detail': FilmDetail
  },

  mounted(){
    fetch('https://ghibliapi.herokuapp.com/films')
    .then(res => res.json())
    .then(filmsRes => this.films = filmsRes)

    eventBus.$on( 'film-selected', (film) => {
      this.selectedFilm = film;
    })
  }

}
</script>

<style scoped>
body {
  background-color: aquamarine;
}
h1 {
  font-family: sans-serif;
  color: red;
}
</style>
