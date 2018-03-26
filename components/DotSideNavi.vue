<!-- Side Scroll Dot Navi -->
<template>
  <div class="dot-side-nav">
    <dot-navi-elem v-for="(n, index) in 4"
                   v-bind:key="index"
                   v-bind:class="{ 'active': index === 0 }"
                   v-bind:id="index"
    />
  </div>
</template>

<script>
  import DotNaviElem from '~/atoms/DotNaviElem.vue';

  export default {
    components: {
      DotNaviElem
    }
  };
</script>

<style lang="scss" scoped>
  @import '../assets/styles';

  .dot-side-nav {
    position: absolute;
    text-align: center;
    bottom: $space_5;
    left: 0;
    width: 100%;
    z-index: 50;
  }
</style>
