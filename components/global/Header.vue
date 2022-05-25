<template>
  <nav class="nav" aria-label="Main Menu">
    <div class="nav-skew">
        <div class="nav-logoWrapper">
          <FameStar class="nav-logo" />
        </div>
        <ul class="nav-wrapper">
          <li class="nav-item">
            <nuxt-link class="nav-link" to="/">Accueil</nuxt-link>
          </li>
          <li class="nav-item">
            <nuxt-link class="nav-link" to="/horaire">Horaire</nuxt-link>
          </li>
          <li class="nav-item">
            <nuxt-link class="nav-link" to="/saison">Saison</nuxt-link>
          </li>
          <li class="nav-item">
            <nuxt-link class="nav-link" to="/entraineur">Entraineurs</nuxt-link>
          </li>
          <li class="nav-item">
            <nuxt-link class="nav-link" to="/contact">contact</nuxt-link>
          </li>
        </ul>
    </div>
  </nav>
</template>

<script>
import FameStar from '~/components/icons/fameStar.svg?inline'
export default {
  name: 'Header',

  components: {
    FameStar
  }
}
</script>

<style lang="scss">
  @import '@/assets/sass/_variables.scss';
  .nav {
    position: absolute;
    top: 0;
    display: flex;
    width: 100%;
    margin-bottom: 1.6%;
    z-index: 10;
  }

  .nav-skew {
    display: flex;
    width: 100%;
    padding: 0 5%;
    margin-top: 1.6%;
    background-color: $fame;
    transform: skew(0deg, -2deg);
  }

  .nav-logoWrapper {
    margin: 0 5% 0 0;
    display: flex;
    height: 100%;
    min-width: 182px;
    width: fit-content;
    position: relative;
    box-sizing: border-box;
  }

  .nav-logo {
    position: absolute;
    display: flex;
    box-sizing: border-box;
    top: -35px;
  }

  .nav-wrapper {
    display: flex;
    width: 100%;
    justify-content: space-between;
  }

  .nav-item {
    transform: skew(2deg, 2deg);
  }

  .nav-link {
    @extend %navText;
  }
</style>
