<template>
  <div class="social-links">
    <ul>
      <li><a href="https://github.com/stavros-liaskos" target="_blank">
        <i class="fab fa-github"></i>
      </a></li>
      <li><a href="https://bitbucket.org/stavros_liaskos/" target="_blank">
        <i class="fab fa-bitbucket"></i>
      </a></li>
      <li><a href="https://codepen.io/stavros-liaskos/#" target="_blank">
        <i class="fab fa-codepen"></i>
      </a></li>
      <li><a href="https://www.linkedin.com/in/stavros-liaskos-66166094/" target="_blank">
        <i class="fab fa-linkedin-in"></i>
      </a></li>
      <li><a href="https://www.xing.com/profile/Stavros_Liaskos" target="_blank">
        <i class="fab fa-xing"></i>
      </a></li>
      <li><a href="mailto:st.liaskos@gmail.com" target="_blank">
        <i class="fab fas fa-envelope"></i>
      </a></li>
    </ul>
  </div>
</template>

<style lang="scss" scoped>
  @import '../assets/styles';

  .social-links {
    display: none;
  }

  @include breakpoint($breakpoint_screen_md) {
    .social-links {
      display: block;
      position: absolute;
      bottom: $space_8;
      left: 0;

      .fab {
        font-size: $navi_toolbar_icons_size;
        cursor: pointer;
      }
    }
  }
</style>
