<template>
  <div v-if="hasCocktails">
    <div
      id="whiteColor"
      class="mycontainer"
      v-for="(element, index) in cocktails"
      v-bind:key="index"
    >
      <b-media right-align vertical-align="center">
        <template #aside>
          <b-img
            :src="element.strDrinkThumb"
            width="180"
            alt="placeholder"
          ></b-img>
        </template>
        <h5 class="mt-0 mb-1">{{ element.strDrink }}</h5>

        <h6>Ingredients:</h6>
        <div class="myFlex">
          <p class="mb-0">{{ element.strIngredient1 }}&nbsp;</p>
          <p class="mb-0" v-if="element.strMeasure1">
            {{ element.strMeasure1 }}
          </p>

          <p class="mb-0" v-if="element.strIngredient2">
            , {{ element.strIngredient2 }}&nbsp;
          </p>
          <p class="mb-0" v-if="element.strMeasure2">
            {{ element.strMeasure2 }}
          </p>

          <p class="mb-0" v-if="element.strIngredient3">
            , {{ element.strIngredient3 }}&nbsp;
          </p>
          <p class="mb-0" v-if="element.strMeasure3">
            {{ element.strMeasure3 }}
          </p>

          <p class="mb-0" v-if="element.strIngredient4">
            , {{ element.strIngredient4 }}&nbsp;
          </p>
          <p class="mb-0" v-if="element.strMeasure4">
            {{ element.strMeasure4 }}
          </p>

          <p class="mb-0" v-if="element.strIngredient5">
            , {{ element.strIngredient5 }}&nbsp;
          </p>
          <p class="mb-0" v-if="element.strMeasure5">
            {{ element.strMeasure5 }}
          </p>

          <p class="mb-0" v-if="element.strIngredient6">
            , {{ element.strIngredient6 }}&nbsp;
          </p>
          <p class="mb-0" v-if="element.strMeasure6">
            {{ element.strMeasure6 }}
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
#whiteColor {
  color: white;
}
.mycontainer {
  width: 80vw;
  margin: auto;
  padding: 60px;
}
.myFlex {
  display: flex;
  text-align: center;
  align-items: center;
}
</style>