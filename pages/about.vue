<template>
  <div class="myBackground">
    <Titre :titre="titre" />
    <div class="whiteColor aboutText">
      <vue-typed-js
        :typeSpeed="60"
        :startDelay="200"
        :backSpeed="20"
        :backDelay="200"
        :loop="true"
        :showCursor="false"
        :cursorChar="'_'"
        :strings="[
          ` Hi, my name is alexandre i was a watchmaker, and now i want to be a
        developper. So i made this app for learn Nuxt.js`,
          ` You can try to find a nice cocktail just type something like:
        kir, martini, mojito etc..`,
          `Have fun !`,
        ]"
      >
        <p class="typing"></p>
      </vue-typed-js>
    </div>
  </div>
</template>

<script>
import Titre from '../components/Titre'
import { VueTypedJs } from 'vue-typed-js'
export default {
  components: { Titre, VueTypedJs },
  data() {
    return {
      titre: 'About',
    }
  },
  head() {
    return {
      title: 'Cocktail search',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'About cocktail',
        },
      ],
    }
  },
}
</script>

<style>
.aboutText {
  padding: 40px;
  width: 80vw;
  margin: auto;
  font-size: 1.5rem;
}
</style>