<template>
  <div class="burger-menu"
       v-on:click=clickHandler()
       v-bind:class="{ active: isNavOpen}"
  >
    <span class="burger-menu-line burger-menu-line-0"></span>
    <span class="burger-menu-line burger-menu-line-1"></span>
    <span class="burger-menu-line burger-menu-line-2"></span>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        isNavOpen: false
      };
    },

    methods: {
      naviStateChange() {
        this.$root.$emit('toggle.navigation.state', this.isNavOpen);
      },
      toggleNavClass() {
        this.isNavOpen = !this.isNavOpen;
      },
      clickHandler() {
        this.naviStateChange();
        this.toggleNavClass();
      }
    }
  };
</script>

<style lang="scss" scoped>
  @import '../assets/styles';

  // Burger menu variables
  $burger_menu_width: $space_5;
  $burger_menu_height: 26px;
  $burger_menu_line_height: 2px;
  $burger-menu-color: $color_blue;

  .burger-menu {
    position: absolute;
    top: $space_2;
    right: $space_2;
    width: $burger_menu_width;
    height: $burger_menu_height;
    cursor: pointer;
    transition: opacity .25s ease;

    &:hover {
      // spin animation
      .burger-menu-line-0 {
        animation: spin $spin_duration linear;
      }
      .burger-menu-line-1 {
        animation: spin $spin_duration 0.1s linear;
      }
      .burger-menu-line-2 {
        animation: spin $spin_duration 0.2s linear;
      }
    }

    &.active {
      // rotate animation
      .burger-menu-line-0 {
        transform: translateY(7px) translateX(0) rotate(45deg)
      }
      .burger-menu-line-1 {
        opacity: 0
      }
      .burger-menu-line-2 {
        transform: translateY(-11px) translateX(0) rotate(-45deg)
      }

      &:hover {
        // disable animation when hover+active
        .burger-menu-line-0 {
          animation: 0;
        }
        .burger-menu-line-1 {
          animation: 0;
        }
        .burger-menu-line-2 {
          animation: 0;
        }
      }
    }

    .burger-menu-line {
      border: none;
      background: $burger-menu-color;
      height: $burger_menu_line_height;
      width: 100%;
      position: absolute;
      left: 0;
      transition: all .35s ease;
      cursor: pointer;

    }

    @for $i from 0 through 3 {
      .burger-menu-line-#{$i} {
        top: $i*8px;
      }
    }
  }

  @include breakpoint($breakpoint_screen_md) {
    .burger-menu {
      top: $space_8;
      left: $space_2;
      width: $burger_menu_width;
      height: $burger_menu_height;
    }
  }
</style>
