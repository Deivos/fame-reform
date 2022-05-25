<template>
  <main>
    <h1 class="home-title">
      <span class="home-titleFull">{{ home.title_1 }}</span>
      <span class="home-titleBorder">{{ home.title_2 }}</span>
    </h1>
  </main>
</template>

<script>
export default {
  async asyncData({ $content }) {
    const home = await $content("home").fetch();

    return {
      home,
    };
  },
};
</script>

<style lang="scss">
  @import '@/assets/sass/_variables.scss';

 .home-titleFull {
   @extend %title-white;
 }

 .home-titleBorder {
   @extend %title-border;
 }

</style>
