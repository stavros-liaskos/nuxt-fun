<!-- Slide-In Navigation Menu -->
<template>
  <div class="navigation" v-bind:class="{ active: isNavOpen}">
    <navi-toolbar/>

    <div class="menu-container">
      <ul>

        <li class="menu-item underline">
          <nuxt-link v-on:click.native='navBarHandler(isNavOpen)' class="item-link" to="/">
            Home
          </nuxt-link>
        </li>

        <li class="menu-item flip">
          <nuxt-link v-on:click.native='navBarHandler(isNavOpen)' class="item-link" to="/Contact">
            Contact
          </nuxt-link>
        </li>

        <li class="menu-item">
          <nuxt-link v-on:click.native='navBarHandler(isNavOpen)' class="item-link underline" to="/Contact">
            Whateva
          </nuxt-link>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
  import NaviToolbar from './NaviToolbar.vue';

  export default {
    components: {
      NaviToolbar
    },

    data() {
      return {
        isNavOpen: false
      };
    },

    methods: {
      initNavigationListener() {
        this.$root.$on('toggle.navigation.state', (isNaviOpen) => {
          this.isNavOpen = !isNaviOpen;
        });
      }
    },

    mounted() {
      this.initNavigationListener();
    }
  };
</script>

<style lang="scss" scoped>
  @import '../assets/styles';

  .navigation {
    background: $color_black;
    position: fixed;
    height: 100%;
    top: -100%;
    left: 0;
    right: 0;
    transition: top 1s;
    z-index: 60;

    &.active {
      top: 0;
    }

    .menu-container {
      position: absolute;
      top: 40%;
      width: 80%;
      margin: 0 10%;

      .menu-item {
        display: inline-block;
        margin: 25px 0 25px 50px;
        width: auto;
      }
    }
  }

  @include breakpoint($breakpoint_screen_md) {
    .navigation {
      width: 100%;
      height: 100%;
      left: -100%;
      top: unset;
      transition: left 1s;

      &.active {
        left: 0;
      }
    }
  }
</style>
