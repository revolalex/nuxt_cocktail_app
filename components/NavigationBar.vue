<template>
  <div>
    <b-navbar toggleable="lg" type="dark" variant="info">
      <b-navbar-brand href="#">🍸</b-navbar-brand>
      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav>
          <b-nav-item href="#"
            ><nuxt-link to="/">Cocktail</nuxt-link></b-nav-item
          >
          <b-nav-item href="#"
            ><nuxt-link to="/ingredient">Ingredient</nuxt-link></b-nav-item
          >
          <b-nav-item href="#"
            ><nuxt-link to="/about">About</nuxt-link></b-nav-item
          >
          <b-nav-item href="#"
            ><nuxt-link to="/contact">Contact</nuxt-link></b-nav-item
          >
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
  </div>
</template>

<script>
export default {
  name: 'NavigationBar',
}
</script>

<style>
/* exact link will show the primary color for only the exact matching link */
a.nuxt-link-exact-active {
  color: #ffffff;
}
a {
  color: #000000;
}
</style>