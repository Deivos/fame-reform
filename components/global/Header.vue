<template>
  <nav class="nav" aria-label="Main Menu">
    <div class="nav-skew">
        <div class="nav-logoWrapper">
          <IconsFameStar />
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
export default {
  name: 'Header'
}
</script>

<style lang="scss">
  @import '@/assets/sass/_variables.scss';
  .nav {
    display: flex;
    width: 100%;
  }

  .nav-skew {
    display: flex;
    width: 100%;
    margin-top: 2.6%;
    background-color: $fame;
    transform: skew(0deg, -2deg);
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
