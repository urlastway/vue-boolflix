<template>
  <section>
      <div>
          <SearchBar />
      </div>
      <div class="containter">
        <div class="CardCharacter__content">
          <CardCharacters v-for="character in characters" :key="character.id" :character="character"/>
        </div>
      </div>
  </section>
</template>


<script>

import axios from 'axios';
import CardCharacters from '../commons/CardCharacters.vue';
import SearchBar from '../commons/SearchBar.vue';

export default {
    name: 'SectionCharacters',
    props: {
    msg: String
    },
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
    created() {
        axios.get('https://api.themoviedb.org/3/search/movie', {
        params: {
            api_key: 'e99307154c6dfb0b4750f6603256716d',
            query: 'ritorno',
            language: 'it-IT',
        }
        }).then((response) => {
            this.characters = response.data.results;
        }).catch((error) => {
        console.log(error);
        })
    },
}
</script>

<style lang="scss" scoped>
.CardCharacter__content{
    color: #fff;
}
</style>