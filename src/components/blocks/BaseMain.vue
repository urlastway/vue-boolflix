<template>
  <main class="main container">
    <h1 class="film__or__movie">Serie TV:</h1>
    <div class="movies__content">
          <div class="movie" v-for="movie in data.movies" :key="movie">
                <img src="https://www.mrw.it/img/cope/0iwkf4_1609360688.jpg">
                <h2 class="movies__title">{{movie.title}}</h2>
                <p class="movies__title__original">{{movie.original_title}}</p>
                <p class="movies__leng">Lingua: <img :src="existFlag(movie.original_language) ? require(`../../assets/img/flags/${movie.original_language}.png`) : null"></p>
                <p class="movies__voto">Voto: {{movie.vote_average}}</p>
          </div>        
    </div>
    <h1 class="film__or__movie">Film:</h1>
        <div class="movies__content">
          <div class="movie" v-for="film in data.films" :key="film">
                <img src="https://www.mrw.it/img/cope/0iwkf4_1609360688.jpg">
                <h2 class="movies__title">{{film.name}}</h2>
                <p class="movies__title__original">{{film.original_name}}</p>
                <p class="movies__leng">Lingua: <img :src="existFlag(film.original_language) ? require(`../../assets/img/flags/${film.original_language}.png`) : null"></p>
                <p class="movies__voto">Voto: {{film.vote_average}}</p>
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
        flagsAviable: [
          'it',
          'en'
        ],
      }
    },
    methods: {
      existFlag(lang) {
            return this.flagsAviable.includes(lang);
        }
    }
}
</script>

<style lang="scss" scoped>

.movies__content{
    display: flex;
    flex-wrap: wrap;
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
    text-align: center;
}
img {
    width: 100%;
    height: auto;
}
.film__or__movie{
  color: #fff;
  text-transform: uppercase;
  font-size: 20px;
}

.movie p img{
  width: 10%;
  margin: 0 10px;
}

</style>