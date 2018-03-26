<template>
  <section class="app"
           v-bind:class="{ active: isNavOpen}"
  >
    <navigation/>

    <div class="container">
      <header-bar/>
      <main-content/>
      <dot-side-navi/>
    </div>
  </section>
</template>

<script>
  import HeaderBar from '~/components/HeaderBar.vue';
  import Navigation from '~/components/Navigation.vue';
  import MainContent from '~/components/MainContent.vue';
  import DotSideNavi from '~/components/DotSideNavi.vue';

  export default {
    components: {
      HeaderBar,
      Navigation,
      MainContent,
      DotSideNavi
    },

    data() {
      return {
        isNavOpen: false
      };
    },

    methods: {
      /**
       * Because I love beer
       */
      beerLog() {
        console.log('🍺');
      },

      /**
       * Initialize Navigation Listener for toggling state of Burger, Navigation, app elements
       */
      initNavigationListener() {
        this.$root.$on('toggle.navigation.state', (isNaviOpen) => {
          this.isNavOpen = !isNaviOpen;
        });
      }
    },

    mounted() {
      this.beerLog();
      this.initNavigationListener();
    }
  };
</script>

<style lang="scss" scoped>
  @import '../assets/styles';

  .app {
    position: relative;
    width: 100%;
    height: 100%;

    .container {
      background: $color_blue;
      height: 100%;
      margin: $navi_toolbar_device_height 0 0 0;
    }
  }

  @include breakpoint($breakpoint_screen_md) {
    .app {
      .container {
        position: relative;
        margin: 0 0 0 $navi_toolbar_desktop_width;
      }
    }
  }
</style>
