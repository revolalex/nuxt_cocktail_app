<template>
  <div>
    <div class="mycontainer">
      <b-card
        no-body
        class="overflow-hidden mx-auto"
        style="max-width: 580px"
        border-variant="info"
      >
        <b-row no-gutters>
          <b-col md="6">
            <b-card-img
              id="imgCocktailDetail"
              :src="cocktail[0].strDrinkThumb"
              alt="Image"
              class="rounded-0"
            ></b-card-img>
          </b-col>
          <b-col md="6">
            <b-card-body :title="cocktail[0].strDrink">
              <b-card-text>
                <h6>Ingredients:</h6>
                {{ cocktail[0].strIngredient1 }}:&nbsp;
                <span v-if="cocktail[0].strMeasure1">
                  {{ cocktail[0].strMeasure1 }}
                </span>
                <span v-if="cocktail[0].strIngredient2">
                  , {{ cocktail[0].strIngredient2 }}:&nbsp;
                  <span v-if="cocktail[0].strMeasure2">
                    {{ cocktail[0].strMeasure2 }}
                  </span>
                </span>
                <span v-if="cocktail[0].strIngredient3">
                  , {{ cocktail[0].strIngredient3 }}:&nbsp;
                  <span v-if="cocktail[0].strMeasure3">
                    {{ cocktail[0].strMeasure3 }}
                  </span>
                </span>
                <span v-if="cocktail[0].strIngredient4">
                  , {{ cocktail[0].strIngredient4 }}:&nbsp;
                  <span v-if="cocktail[0].strMeasure4">
                    {{ cocktail[0].strMeasure4 }}
                  </span>
                </span>
                <span v-if="cocktail[0].strIngredient5">
                  , {{ cocktail[0].strIngredient5 }}:&nbsp;
                  <span v-if="cocktail[0].strMeasure5">
                    {{ cocktail[0].strMeasure5 }}
                  </span>
                </span>
                <span v-if="cocktail[0].strIngredient6">
                  , {{ cocktail[0].strIngredient6 }}:&nbsp;
                  <span v-if="cocktail[0].strMeasure6">
                    {{ cocktail[0].strMeasure6 }}
                  </span>
                </span>
                <hr />
                <h6>Instruction:</h6>
                {{ cocktail[0].strInstructions }}
              </b-card-text>
              <b-button href="#" variant="dark" @click="closeClicked"
                >Close</b-button
              >
            </b-card-body>
          </b-col>
        </b-row>
      </b-card>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Cocktail',
  props: {
    cocktail: Array,
  },
  methods: {
    closeClicked() {
      this.$emit('closeClicked')
    },
  },
}
</script>

<style>
#imgCocktailDetail {
  object-fit: cover;
  min-height: 100%;
}
</style>