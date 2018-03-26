<template>
  <div class="portfolio">
    <h1>HEY</h1>

    <div class="project-cards-container">

      <project-card v-for="(projectCard, index) in projectCards" v-if="projectCards.length"
                    v-bind:imgUrl="projectCard.imgUrl"
                    v-bind:title="projectCard.title"
                    v-bind:tech="projectCard.tech"
                    v-bind:desc="projectCard.desc"
                    v-bind:key="index"
      />

    </div>
  </div>
</template>

<script>
  import ProjectCard from '~/organisms/ProjectCard.vue';

  export default {
    components: {
      ProjectCard
    },

    data() {
      return {
        projectCards: [
          {
            imgUrl: 'http://via.placeholder.com/300x200',
            title: 'Another project',
            tech: 'Vue, scss',
            desc: 'Blah blah blah Blah blah blah Blah blah blah'
          },
          {
            imgUrl: 'http://www.fillmurray.com/200/200',
            title: 'A murray project',
            tech: 'Vue, scss',
            desc: 'Blah blah blah Blah blah blah Blah blah blah'
          },
          {
            imgUrl: 'http://via.placeholder.com/200x200',
            title: 'Another project',
            tech: 'Vue, scss',
            desc: 'Blah blah blah Blah blah blah Blah blah blah'
          },
          {
            imgUrl: 'http://www.placecage.com/200/200',
            title: 'A murray project',
            tech: 'Vue, scss',
            desc: 'Blah blah blah Blah blah blah Blah blah blah'
          }
        ]
      };
    }
  };
</script>

<style lang="scss" scoped>
  .portfolio {
    background: inherit;

    .project-cards-container {
      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
    }
  }
</style>
