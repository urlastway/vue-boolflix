<template>
  <main class="main container">
    <div class="movies__content">
          <div class="movie" v-for="movie in data.movies" :key="movie">
                <img src="https://www.mrw.it/img/cope/0iwkf4_1609360688.jpg">
                <h2 class="movies__title">{{movie.title}}</h2>
                <p class="movies__title__original">{{movie.original_title}}</p>
                <p class="movies__languege">Lingua: {{movie.original_language}}</p>
                <p class="movies__voto">Voto: {{movie.vote_average}}</p>
          </div>          
    </div>
  </main>
</template>

<script>

import data from '../../shared/data'

export default {
    name: 'BaseMain',
    components: {
    },
    data(){
      return{
        data,
      }
    }
}
</script>

<style lang="scss" scoped>

.movie__content{
    display: flex;
    margin: 20px 0;
}
.movie{
    width: 400px;
    height: auto;
    display: flex;
    flex-direction: column;
    background-color: var(--background-cards);
    color: var(--color-cards);
    padding: 2rem;
    margin: 5px;
}
img {
    width: 200px;
    height: 200px;
}

</style>