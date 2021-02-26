<template>
  <div>
    <b-navbar toggleable="lg" type="dark" variant="dark">
      <nuxt-link to="/">🍸</nuxt-link>
      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav>
          <b-nav-item href="#"
            ><nuxt-link to="/">Cocktail</nuxt-link></b-nav-item
          >
          <b-nav-item href="#"
            ><nuxt-link to="/liquor">Liquor</nuxt-link></b-nav-item
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
  color: #faf705;
  text-shadow: 0 0 5px #dddddd, 0 0 10px #a5f1ff, 0 0 20px #000000,
    0 0 30px #d8fdd5, 0 0 40px #d8fdd5;
}
a {
  letter-spacing: 0.2rem;
  font-size: 1.1rem;
  color: #fc2192;
  text-shadow: 0 0 1px #f700b9, 0 0 1px #a5f1ff, 0 0 2px #b75e8c,
    0 0 3px #f06aaf, 0 0 40px #b75e8c;
}
a:hover {
  color: #faf705;
  text-shadow: 0 0 5px #dddddd, 0 0 10px #a5f1ff, 0 0 20px #000000,
    0 0 30px #d8fdd5, 0 0 40px #d8fdd5;
}
</style>