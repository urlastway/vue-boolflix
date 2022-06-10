<template>
  <section class="container">
      <div class="cards__content">
          <div class="cards" v-for="card in 12" :key="card">
                <img src="https://www.mrw.it/img/cope/0iwkf4_1609360688.jpg">
                <h2 class="cards__title">Titolo</h2>
                <p class="cards__title__original">Titolo Originale</p>
                <p class="cards__languege">Lingua</p>
                <p class="cards__voto">Voto: 9</p>
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
    flex-wrap: wrap;
    margin: 20px 0;
    justify-content: center;
}
.cards{
    display: flex;
    flex-direction: column;
    background-color: var(--background-cards);
    color: var(--color-cards);
    padding: 2rem;
    margin: 5px;
}
</style>