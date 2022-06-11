<template>
  <section class="container">
      <div class="cards__content">
          <div class="cards">
                <img src="https://www.mrw.it/img/cope/0iwkf4_1609360688.jpg">
                <h2 class="cards__title">{{character.title}}</h2>
                <p class="cards__title__original">{{character.original_title}}</p>
                <p class="cards__languege">Lingua: {{character.original_language}}</p>
                <p class="cards__voto">Voto: {{character.vote_average}}</p>
          </div>          
      </div>

  </section>
</template>

<script>
export default {
    name: 'CardCharacters',
    props: {
        character: Object,
    }
}
</script>

<style>
.cards__content{
    display: flex;
    margin: 20px 0;
}
.cards{
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