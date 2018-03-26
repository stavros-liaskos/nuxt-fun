<template>
  <div class="project-card">
    <div class="img-wrapper">
      <img class="project-card-img" v-bind:src="[imgUrl]" v-bind:alt="[title]">
    </div>

    <div class="texts-container">
      <div class="title-container">
        <h4>{{title}} </h4>
      </div>

      <div class="desc-container">
        <p>{{desc}}</p>
      </div>

      <div class="tech-stack-container">
        <p>{{tech}}</p>
      </div>
    </div>
  </div>

</template>

<script>
  export default {
    props: {
      imgUrl: String,
      title: String,
      tech: String,
      desc: String
    }
  };
</script>

<style lang="scss" scoped>
  @import '../assets/styles';

  // Card spacing
  $card_width: 200px;
  $card_height: 300px;
  $card_bg_color: pink;
  $anim-time: .3s;

  .project-card {
    position: relative;
    width: $card_width;
    height: $card_height;
    background: $card_bg_color;
    margin: 0 $space_2 $space_7;
    z-index: 1;

    .img-wrapper {
      overflow: hidden;

      .project-card-img {
        opacity: 1;
        transition: all $anim-time linear 0s;
      }
    }

    .texts-container {
      position: absolute;
      bottom: 0;
      background: inherit;
      padding: $space_1 $space_2;
      width: 100%;
      height: $space_7;
      transition: all $anim-time linear 0s;

      .desc-container {
        display: none;
        opacity: 0;
      }

      .tech-stack-container {
        position: absolute;
        bottom: 0;
        background: $card_bg_color;
      }
    }

    &:hover {
      .project-card-img {
        transform: scale(1.1);
        opacity: .6;
      }

      .texts-container {
        height: $space_8;

        .desc-container {
          display: block;
          opacity: 1;
          height: $space_7;
        }
      }
    }
  }

</style>
