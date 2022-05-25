<template>
  <div class="wrapper">
    <Header />
    <nuxt />
  </div>
</template>

<style lang="scss">
  @import '@/assets/sass/_variables.scss';
  .wrapper {
    position: relative;
    padding-top: 8%;
    min-height: 100vh;
    background-color: $gray;
  }

</style>
