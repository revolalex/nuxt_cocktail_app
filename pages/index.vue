<template>
  <div class="myBackground">
    <Titre :titre="titre" />
    <Search v-on:searchClicked="searchWasClicked" />
    <Table v-if="cocktails" v-bind:cocktails="cocktails" />
  </div>
</template>

<script>
import axios from 'axios'
import Search from '../components/Search'
import Table from '../components/Table'
import Titre from '../components/Titre'

export default {
  components: {
    Search,
    Table,
    Titre,
  },
  data() {
    return {
      cocktails: null,
      titre: 'Cocktail name',
    }
  },
  computed: {
    hasCocktails() {
      if (this.cocktails != null) {
        return true
      } else {
        return false
      }
    },
  },
  methods: {
    async searchWasClicked(text) {
      const res = await axios.get(
        `https://www.thecocktaildb.com/api/json/v1/1/search.php?s=${text}`
      )
      this.cocktails = res.data.drinks
      console.log(this.cocktails)
    },
  },
  head() {
    return {
      title: 'Cocktail search',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Search a cocktail',
        },
      ],
    }
  },
}
</script>

<style>
html,
body {
  max-width: 100%;
  overflow-x: hidden;
}
body {
  font-size: 16px;
}
input,
select {
  font-size: 100%;
}
/* Backgroun image */
.myBackground {
  background: url('../assets/bg.png');
  /* Full height */
  min-height: 100vh;
  height: 100%;
  /* Create the parallax scrolling effect */
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  overflow: hidden;
  background-attachment: fixed;
}
/* iphone X */ /* Iphone 11 */
@media only screen and (device-width: 375px) and (device-height: 812px) and (-webkit-device-pixel-ratio: 3) {
  .myBackground {
    background: url('../assets/bg.png');
    -webkit-background-size: 100%;
    -moz-background-size: 100%;
    -o-background-size: 100%;
    background-size: 100%;
    -webkit-background-size: cover;
    -moz-background-size: cover;
    -o-background-size: cover;
    background-size: cover;
  }
}
@media only screen and (device-width: 414px) and (device-height: 896px) and (-webkit-device-pixel-ratio: 2) {
  .myBackground {
    background: url('../assets/bg.png');
    -webkit-background-size: 100%;
    -moz-background-size: 100%;
    -o-background-size: 100%;
    background-size: 100%;
    -webkit-background-size: cover;
    -moz-background-size: cover;
    -o-background-size: cover;
    background-size: cover;
  }
}
</style>