<template>
  <div class="myBackground">
    <Titre :titre="titre" />
    <a href="https://github.com/revolalex"><img id="gitLogo" src="../assets/git.png" alt="" /></a>

    <a href="https://www.linkedin.com/in/alexandre-rodrigueza/"><img id="gitLogo" src="https://upload.wikimedia.org/wikipedia/commons/thumb/c/ca/LinkedIn_logo_initials.png/768px-LinkedIn_logo_initials.png" alt="" /></a>
  </div>
</template>

<script>
import Titre from '../components/Titre'
export default {
  components: { Titre },
  data() {
    return {
      titre: 'Contact',
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
#gitLogo {
  padding-top: 40px;
  width: 100px;
  height: auto;
  margin: auto;
  display: block;
  margin-left: auto;
  margin-right: auto;
}
#gitLogo:hover{

}
</style>