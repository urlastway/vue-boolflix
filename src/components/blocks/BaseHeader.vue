<template>
  <header class="header__inner">
      <div class="header__inner__logo">
          <h1 class="logo">Boolflix</h1>
      </div>
  </header>
</template>

<script>
export default {
    name: 'BaseHeader',
    components: {

    },
}
</script>

<style lang="scss" scoped>

    .header__inner{

        width: 100%;
        height: auto;
        padding: 1rem 0;
    }
    .logo{
        color: var(--logo__color);
        margin-left: 10px;
    }
</style>