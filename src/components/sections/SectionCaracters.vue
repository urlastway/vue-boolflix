<template>
  <section>
      <div>
          <SearchBar />
      </div>
      <div>
          <CardCharacters class="col-12"/>
      </div>
  </section>
</template>


<script>

import axios from 'axios';
import { response } from 'express';
import CardCharacters from '../commons/CardCharacters.vue';
import SearchBar from '../commons/SearchBar.vue';

export default {
    name: 'SectionCharacters',
    data(){
      return{
          characters: [],
          FilterCharacters: [],
      }  
    },
    components:{
        CardCharacters,
        SearchBar,
    },
    created(){
        axios.get('https://api.themoviedb.org/3/search/movie', {
            params: {
            api_key: 'e99307154c6dfb0b4750f6603256716d',
            query: 'ritorno al futuro',
            language: 'it-IT',
            }
        }).then((response) =>{
            console.log(response);
        }).catch((error) => {
            console.log(error);
        });
    },
}
</script>

<style>

</style>