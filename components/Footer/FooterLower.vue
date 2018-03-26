<template>
  <div class="footer-lower">
    <div class="footer-lower-left">
      <ul>
        <li>© {{dateYear}} Stavros Liaskos</li>
      </ul>
    </div>

    <div class="footer-lower-right">
      <ul>
        <li><a href="/privacy-policy">Privacy Policy</a></li>
        <li><a href="https://google.com/">Sitemap</a></li>
        <li><a href="/contact">Support</a></li>
      </ul>
    </div>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        dateYear: new Date().getFullYear()
      };
    }
  };
</script>

<style lang="scss" scoped>
  @import '../../assets/styles';

  .footer-lower {
    .footer-lower-left {
      float: left;
    }

    .footer-lower-right {
      float: right;
    }

    li {
      display: inline;
    }
  }
</style>
