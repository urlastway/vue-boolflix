<template>
  <div id="app">
    <body>
      <BaseHeader />
      <BaseMain />
      <BaseFooter />
    </body>
  </div>
</template>

<script>
import BaseHeader from './components/blocks/BaseHeader.vue';
import BaseMain from './components/blocks/BaseMain.vue';
import BaseFooter from './components/blocks/BaseFooter.vue';


export default {
  name: 'App',
  components: {
    BaseHeader,
    BaseMain,
    BaseFooter
}
}
</script>

<style lang="scss">

@import './assets/style/global.scss';

body{
  background-color: var(--background-main-color);
}

</style>
