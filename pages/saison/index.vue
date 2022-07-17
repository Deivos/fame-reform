<template>
  <main>
    <h1 class="season-title">
      <span class="season-titleFull">{{ season.title }}</span>
    </h1>
  </main>
</template>

<script>
export default {
  async asyncData({ $content }) {
    let season = await $content("season").fetch();
    season = season[0]
    return {
      season,
    };
  },
};
</script>

<style lang="scss">
  @import '@/assets/sass/_variables.scss';

  .season-wrapper {
    position: relative;
    display: flex;
    justify-content: space-between;
    height: 100%;
    flex-grow: 1;
    z-index: 2;
  }

  .season-background {
    position: absolute;
    top: -5%;
    right: 0;
    left: 0;
    height: calc(100vh + 5%);
    background: url('~assets/img/hours_background.jpg') no-repeat;
    background-size: cover;
    z-index: 1;
  }

  .season-title {
    @extend %title-white;
    margin: 3%;
    z-index: 2;
  }
</style>
