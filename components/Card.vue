<template>
  <div class="myContainerCard">
    <b-card-group deck>
      <b-card
        overlay
        text-variant="white"
        v-for="element in cocktails"
        v-bind:key="element.idDrink"
        :title="element.strDrink"
        :img-src="element.strDrinkThumb"
        img-alt="Cocktail"
        img-top
        style="min-width: 12rem"
        class="mb-4 mt-4 myCard"
      >
        <template #footer>
          <a id="myLinkCard" href="#" @click="detailClicked(element.idDrink)"
            >Detail</a
          >
        </template>
      </b-card></b-card-group
    >
  </div>
</template>

<script>
export default {
  name: 'Card',
  props: {
    cocktails: Array,
  },
  methods: {
    detailClicked(id) {
      this.$emit('detailClicked', id)
    },
  },
}
</script>

<style>
.myCard {
  text-shadow: 3px 3px 2px rgb(255, 0, 212);
  opacity: 0.8;
}
.myContainerCard {
  width: 90vw;
  margin: auto;
  padding: 60px;
}
#myLinkCard {

  font-weight: 600;
  font-size: 1.1rem;
  text-shadow: none;
  color: #14A3B8;
}


.myCard:hover {
 opacity: 1;
}

</style>