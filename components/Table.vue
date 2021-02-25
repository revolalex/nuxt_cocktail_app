<template>
  <div v-if="hasCocktails">
    <div
      class="mycontainer whiteColor"
      v-for="(element, index) in cocktails"
      v-bind:key="index"
    >
      <b-media right-align vertical-align="center">
        <template #aside>
          <b-img
            :src="element.strDrinkThumb"
            id="cocktailImg"
            alt="placeholder"
          ></b-img>
        </template>
        <h4 class="mt-0 mb-1">{{ element.strDrink }}</h4>

        <h6>Ingredients:</h6>
        <div>
          <p class="mb-0">
            {{ element.strIngredient1 }}&nbsp;
            <span v-if="element.strMeasure1">
              {{ element.strMeasure1 }}
            </span>
            <span v-if="element.strIngredient2">
              , {{ element.strIngredient2 }}&nbsp;
              <span v-if="element.strMeasure2">
                {{ element.strMeasure2 }}
              </span>
            </span>
            <span v-if="element.strIngredient3">
              , {{ element.strIngredient3 }}&nbsp;
              <span v-if="element.strMeasure3">
                {{ element.strMeasure3 }}
              </span>
            </span>
            <span v-if="element.strIngredient4">
              , {{ element.strIngredient4 }}&nbsp;
              <span v-if="element.strMeasure4">
                {{ element.strMeasure4 }}
              </span>
            </span>
            <span v-if="element.strIngredient5">
              , {{ element.strIngredient5 }}&nbsp;
              <span v-if="element.strMeasure5">
                {{ element.strMeasure5 }}
              </span>
            </span>
            <span v-if="element.strIngredient6">
              , {{ element.strIngredient6 }}&nbsp;
              <span v-if="element.strMeasure6">
                {{ element.strMeasure6 }}
              </span>
            </span>
          </p>
        </div>
        <br />
        <h6>Instructions:</h6>
        <p>{{ element.strInstructions }}</p>
      </b-media>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Table',
  props: {
    cocktails: Array,
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
}
</script>

<style>
.whiteColor {
  color: white;
}
.mycontainer {
  width: 90vw;
  margin: auto;
  padding: 60px;
}
#cocktailImg {
  max-width: 160px;
  height: auto;
}
@media (max-width: 441px) {
  #cocktailImg {
    position: relative;
    top: -110px;
    max-width: 70px;
    max-height: 80px;
  }
  .mycontainer {
    width: 100vw;
  }
}
</style>