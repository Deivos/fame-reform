<template>
  <main class="home">
    <h1 class="home-title">
      <span class="home-titleFull">{{ home.title_1 }}</span>
      <span class="home-titleBorder">{{ home.title_2 }}</span>
    </h1>
    <span class="home-background" />
  </main>
</template>

<script>
export default {
  async asyncData({ $content }) {
    let home = await $content("home").fetch();
    home = home[0]
    return {
      home
    };
  },
};
</script>

<style lang="scss">
  @import '@/assets/sass/_variables.scss';

  .home-title {
    position: relative;
    display: flex;
    flex-direction: column;
    width: fit-content;
    border-bottom: 10px solid white;
    z-index: 2;
  }

  .home-titleFull {
    @extend %title-white;
    display: flex;
  }

  .home-titleBorder {
    @extend %title-border;
    display: flex;
  }

  .home-background {
    position: absolute;
    top: -5%;
    bottom: 0;
    right: 0;
    width: 45%;
    background: url('~assets/img/home_background.jpg');
    background-size: cover;
  }

</style>
