<template>
  <header class="header__inner">
        <div class="header__inner__logo">
            <h1 class="logo">Boolflix</h1>
        </div>
        <form class="gap-3" action="" @submit.prevent='searching'>
            <input type="text" placeholder="Cerca un genere" v-model="searchText">
            <button type="submit" class="btn btn-primary">Cerca</button>
        </form>
  </header>
</template>

<script>

import axios from "axios";
import data from '../../shared/data';


export default {
    name: "BaseHeader",
    data() {
        return {
            data,
            searchText: "",
        };
    },
    methods: {
        searching() {
            axios.get('https://api.themoviedb.org/3/search/movie', {
                params: {
                    api_key: 'e99307154c6dfb0b4750f6603256716d',
                    query: this.searchText,
                    language: 'it-IT',
                }
                }).then((response) => {
                    data.movies = response.data.results;
                }).catch((error) => {
                console.log(error);
                });
            axios.get('https://api.themoviedb.org/3/search/tv', {
                params: {
                    api_key: 'e99307154c6dfb0b4750f6603256716d',
                    query: this.searchText,
                    language: 'it-IT',
                }
                }).then((response) => {
                    data.serieTv = response.data.results;
                }).catch((error) => {
                console.log(error);
                });   
        },
    },
}
</script>

<style lang="scss" scoped>

    .header__inner{

        width: 100%;
        height: 100px;
        padding: 1rem 0;
        display: flex;
        justify-content: space-between;
        padding: 20px 50px;
        align-items: center;

    }
    .logo{
        color: var(--logo__color);
        margin-left: 10px;
    }
     form{
        display: flex;

        input{
            height: 50px;
        }
        button{
            height: 50px;

        }
    }
</style>