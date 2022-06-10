<template>
  <main class="main">
      <CardCharacters />
  </main>
</template>

<script>
import CardCharacters from '../commons/CardCharacters.vue';
export default {
    name: 'BaseMain',
    components: {
    CardCharacters
},
}
</script>

<style lang="scss" scoped>

</style>