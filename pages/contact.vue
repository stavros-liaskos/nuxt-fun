<template>
  <section class="container">

    <navigation/>

    <section class="container bg-dark">
      <header-bar/>
      <h1>CONTACT + SUPPORT</h1>
      <footer-bar/>
    </section>
  </section>
</template>

<script>
  import HeaderBar from '~/components/HeaderBar.vue';
  import Navigation from '~/components/Navigation.vue';
  import FooterBar from '~/components/Footer/FooterBar.vue';

  export default {
    components: {
      HeaderBar,
      Navigation,
      FooterBar
    }
  };
</script>

<style lang="scss" scoped>
</style>
