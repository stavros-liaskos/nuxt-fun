<!-- Dot Navi Element used for Side Dot Navi -->
<template>
 <span class="dot-wrapper "
       v-bind:class="{ active: isCurrentSlide}"
       v-on:click="activateDotNaviElem()"
 >
   <span class="dot"></span>
 </span>
</template>

<script>
  export default {
    data() {
      return {
        isCurrentSlide: false
      };
    },

    methods: {
      /**
       * Deactivate all DotNaviElems and then activate the clicked one
       */
      activateDotNaviElem() {
        // deactivate all????

        // activate current
        this.isCurrentSlide = !this.isCurrentSlide;
      }
    }
  };
</script>

<style lang="scss" scoped>
  @import '../assets/styles';

  // Dot elem variables
  $dot_wrapper_width: $space_3;
  $dot_wrapper_height: $dot_wrapper_width;
  $dot_el_color: $color_white;
  $dot_animation_colour: $color_white;
  $dot_animation_blank_space: 4px;

  .dot-wrapper {
    position: relative;
    display: inline-block;
    width: $dot_wrapper_width;
    height: $dot_wrapper_height;
    transform: rotate(45deg);
    margin: $space_1;
    @include setBorderAnimation($dot_animation_colour, 1px);

    .dot {
      position: absolute;
      display: inline-block;
      top: $dot_animation_blank_space;
      left: $dot_animation_blank_space;
      bottom: $dot_animation_blank_space;
      right: $dot_animation_blank_space;
      background: $dot_el_color;
    }
  }
</style>
