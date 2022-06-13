<template>
  <main class="main container">
    <h1 class="film__or__movie">Film:</h1>
    <div class="movies__content">
          <div class="movie" v-for="movie in data.movies" :key="movie">
            <BaseCard :info="movie" />
          </div>        
    </div>
    <h1 class="film__or__movie">Serie TV:</h1>
        <div class="movies__content">
          <div class="movie" v-for="serie in data.serieTv" :key="serie">
            <BaseCard :info="serie" />
          </div>              
    </div>
  </main>
</template>

<script>

import data from '../../shared/data';
import BaseCard from '../commons/BaseCard'

export default {
    name: 'BaseMain',
    components: {
      BaseCard,
    },
    data(){
      return{
        data,
      }
    },
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
    background-color: var(--background-cards);
    color: var(--color-cards);
    padding: 2rem;
    margin: 5px;
    text-align: center;
}
.film__or__movie{
  color: #fff;
  text-transform: uppercase;
  font-size: 20px;
}

</style>