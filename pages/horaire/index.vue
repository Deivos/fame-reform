<template>
  <main>
    <div class="hours-background"></div>
    <div class="hours-wrapper">
      <h1 class="hours-title">
        <span class="hours-titleFull">{{ hours.title }}</span>
      </h1>
      <div class="hours-image">
        <img :src="hours.hours" alt="">
        <p v-if="hours.over" class="hours-over">{{ hours.over }}</p>
      </div>
    </div>
  </main>
</template>

<script>
export default {
  async asyncData({ $content }) {
    let hours = await $content("hours").fetch();
    hours = hours[0]
    return {
      hours,
    };
  }
};
</script>

<style lang="scss">
  @import '@/assets/sass/_variables.scss';

  .hours-wrapper {
    position: relative;
    display: flex;
    justify-content: space-between;
    height: 100%;
    flex-grow: 1;
    z-index: 2;
  }

  .hours-background {
    position: absolute;
    top: -5%;
    right: 0;
    left: 0;
    height: calc(100vh + 5%);
    background: url('~assets/img/hours_background.jpg') no-repeat;
    background-size: cover;
    z-index: 1;
  }

 .hours-title {
   @extend %title-white;
   margin: 3%;
   z-index: 2;
 }

 .hours-image {
   position: relative;
   display: flex;
   justify-content: center;
   align-items: center;
   width: 50%;

   img {
     width: 100%;
   }
 }

 .hours-over {
   position: absolute;
   @extend %title-white;
   text-align: center;
   z-index: 3;
 }

</style>
