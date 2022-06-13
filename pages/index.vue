<template>
  <main class="home">
    <span class="home-background" />
    <div class="home-wrapper">
      <h1 class="home-title">
        <span class="home-titleFull">{{ home.title_1 }}</span>
        <span class="home-titleBorder">{{ home.title_2 }}</span>
      </h1>
      <div class="home-blur">
        <p class="home-description">{{ home.description_1 }}</p>
        <span class="home-separator">-</span>
        <p class="home-description">{{ home.description_2 }}</p>
        <i class="home-arrow">
          <svg xmlns="http://www.w3.org/2000/svg" width="81.503" height="35.175" viewBox="0 0 81.503 35.175">
            <g id="Group_4" data-name="Group 4" transform="translate(3)">
              <line id="Line_2" data-name="Line 2" x2="57" transform="translate(0 18.66)" fill="none" stroke="#fff" stroke-linecap="round" stroke-width="6"/>
              <path id="Path_1" data-name="Path 1" d="M3329.5,747.015,3351,730.33l-21.5-18.49Z" transform="translate(-3272.5 -711.84)" fill="#fff"/>
            </g>
          </svg>
        </i>
        <a class="home-button" :href="home.button_link" target="_blank">{{ home.button }}</a>
      </div>
    </div>
  </main>
</template>

<script>
import Posts from "~/components/posts/posts";
export default {
  components: {Posts},
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

  .home {
    display: flex;
    flex-direction: column;
    width: 100%;
    height: 100%;
    flex-grow: 1;
  }

  .home-wrapper {
    position: relative;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    height: 100%;
    flex-grow: 1;
    z-index: 2;
  }

  .home-title {
    position: relative;
    display: flex;
    flex-direction: column;
    width: fit-content;
    margin: 3%;
    padding-bottom: 25px;
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
    z-index: 1;
  }

  .home-blur {
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 3%;
    background: rgba(255, 255, 255, 0.19);
    backdrop-filter: blur(10px);
  }

  .home-description {
    @extend %subTitle;
  }

  .home-separator {
    @extend %subTitle;
    margin: 0 10px;
  }

  .home-arrow {
    margin: 0 20px;
  }

  .home-button {
    @extend %button;
  }

</style>
