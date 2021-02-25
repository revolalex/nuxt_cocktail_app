<template>
  <div class="myBackground">
    <div>
      <h1 class="neon">Cocktail hour</h1>
    </div>
    <Search v-on:searchClicked="searchWasClicked" />


    <Table v-if="cocktails" v-bind:cocktails="cocktails"/>  
  </div>
</template>

<script>
import axios from 'axios'
import Search from '../components/Search'
import Table from '../components/Table'

export default {
  components: {
    Search, Table,
  },
  data() {
    return {
      cocktails: null,
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
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
}
/* neon effect */
.neon {
  padding-top: 40px;
  color: #fc2192;
  text-shadow: 0 0 5px #ececec, 0 0 10px #a5f1ff, 0 0 20px #b75e8c,
    0 0 30px #f06aaf, 0 0 40px #b75e8c;
}
.neon:hover {
  color: #faf705;
  text-shadow: 0 0 5px #dddddd, 0 0 10px #a5f1ff, 0 0 20px #000000,
    0 0 30px #d8fdd5, 0 0 40px #d8fdd5;
}

h1 {
  font-family: 'Pacifico', cursive;
  font-size: 7rem;
  text-align: center;
}
</style>