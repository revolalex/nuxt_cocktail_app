<template>
  <div class="myBackground">
    <Titre :titre="titre" />
    <Search v-if="show" v-on:searchClicked="searchWasClicked" />
    <Card
      v-if="show"
      v-bind:cocktails="cocktails"
      v-on:detailClicked="showDetail"
    />
    <Cocktail
      v-bind:cocktail="cocktail"
      v-if="!show"
      v-on:closeClicked="closeWasClicked"
    />
  </div>
</template>

<script>
import axios from 'axios'
import Search from '../components/Search'
import Card from '../components/Card'
import Titre from '../components/Titre'
import Cocktail from '../components/Cocktail'

export default {
  components: {
    Search,
    Card,
    Titre,
    Cocktail,
  },
  data() {
    return {
      show: true,
      cocktails: null,
      titre: 'Liquor',
      cocktail: null,
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
        `https://www.thecocktaildb.com/api/json/v1/1/filter.php?i=${text}`
      )
      this.cocktails = res.data.drinks
    },
    async showDetail(id) {
      const res = await axios.get(
        `https://www.thecocktaildb.com/api/json/v1/1/lookup.php?i=${id}`
      )
      this.cocktail = res.data.drinks
      console.log(this.cocktail)
      this.show = false
    },
    closeWasClicked() {
      this.show = true
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
</style>