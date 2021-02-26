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
/* Backgroun image */
.myBackground {
  min-height: 100vh;
  background: url(https://www.hennessy.com/sites/hennessy_fr/files/2020-01/HEADER_COCKTAIL_2880x1540.jpg)
    no-repeat center center fixed;
    
  /* -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover; */
}
</style>