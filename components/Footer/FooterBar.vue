<template>
  <footer class="footer bg-light">
    <div>
      <h1>TODO</h1>
    </div>

    <footer-lower/>
  </footer>
</template>

<script>
  import FooterLower from './FooterLower.vue';

  export default {

    components: {
      FooterLower
    }
  };
</script>

<style lang="scss" scoped>
  @import '../../assets/styles';

  .footer {
    grid-area: f;
  }
</style>
