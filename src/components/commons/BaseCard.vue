<template>
  <div class="Card">
    <img :src="getLink(info.poster_path)">
        <h2 class="movies__title">{{info.title ? info.title : info.name}}</h2>
        <p class="movies__title__original">{{info.original_title ? info.original_title : info.original_name}}</p>
        <p class="movies__leng">Lingua: <img :src="existFlag(info.original_language) ? require(`../../assets/img/flags/${info.original_language}.png`) : null"></p>
        <p class="movies__voto">Voto: {{info.vote_average}}</p>
  </div>
</template>

<script>
export default {
    name: 'BaseCard',
    props:{
        info: Object,
    },
    data(){
        return {
        flagsAviable: [
          'it',
          'en'
        ],
        }
    },
    methods: {
      existFlag(lang) {
            return this.flagsAviable.includes(lang);
        },
      getLink(link){
        return `https://image.tmdb.org/t/p/w185/${link}`
      },
    }

}
</script>

<style lang="scss" scoped>
img {
    width: 100%;
    height: auto;
}
p img{
  width: 10%;
  margin: 0 10px;
}
</style>