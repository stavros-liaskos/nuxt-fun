<template>
  <div class="main-content">
    <aside class="sidebar sidebar-left"></aside>

    <div class="main-content-wrapper">
      <portfolio/>
    </div>

    <aside class="sidebar sidebar-right"></aside>
  </div>
</template>

<script>
  import Portfolio from '~/components/Portfolio.vue';

  export default {
    components: {
      Portfolio
    }
  };
</script>

<style lang="scss" scoped>
  @import '../assets/styles';

  .main-content {
    display: block;

    .sidebar {
      display: none;
    }
  }

  @include breakpoint($breakpoint_screen_md) {
    .main-content {
      display: grid;
      grid-gap: 5px;
      grid-template-columns: $sidebar_width auto $sidebar_width;
      // al: aside-left, c: content, ar: aside-right
      grid-template-areas: "al c ar";
    }

    .main-content-wrapper {
      grid-area: c;
    }
  }
</style>
