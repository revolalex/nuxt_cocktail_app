<template>
  <div class="myContainerCard">
    <b-card-group deck>
      <b-card
        overlay
        text-variant="white"
        v-for="(element, index) in cocktails"
        v-bind:key="index"
        :title="element.strDrink"
        :img-src="element.strDrinkThumb"
        img-alt="Cocktail"
        img-top

        style="min-width: 12rem"
        class="mb-4 mt-4 myCard"
      >
      </b-card
    ></b-card-group>
  </div>
</template>

<script>
export default {
  name: 'Card',
  props: {
    cocktails: Array,
  },
}
</script>

<style>
.myCard {
  text-shadow: 3px 3px 2px rgb(255, 0, 212);
}
.myContainerCard {
  width: 90vw;
  margin: auto;
  padding: 60px;
}
</style>