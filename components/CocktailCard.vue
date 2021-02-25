<template>
  <div v-if="hasCocktails" class="mycontainer">
    <b-card-group deck>
      <div
        id="cardDiv"
        v-for="(element, index) in cocktails"
        v-bind:key="index"
      >
        <b-card
          :title="element.strDrink"
          :img-src="element.strDrinkThumb"
          img-alt="Cocktail"
          img-top
          tag="article"
          style="max-width: 20rem"
          class="mb-2"
        >
          <b-card-text>
            {{ element.strIngredient1 }}, {{ element.strIngredient2 }},
            {{ element.strIngredient3 }}...
          </b-card-text>

          <b-button href="#" variant="primary">More Info</b-button>
        </b-card>
      </div>
    </b-card-group>
  </div>
</template>

<script>
export default {
  name: 'CocktailCard',
  props: { cocktails: Array },
}
</script>

<style>
</style>