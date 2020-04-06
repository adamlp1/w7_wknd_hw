<template>
  <div v-if='film'>
    <h2>{{film.title}}</h2>
    <p>Synopsis: {{film.description}}</p>
    <p>Produced by: {{film.producer}}</p>
    <p>Directed by: {{film.director}}</p>
    <p>Released: {{film.release_date}}</p>
    </div>
</template>

<script>
export default {
  name: 'film-detail',
  props: ['film']

}
</script>

<style scoped>
p {
  font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
}

</style>