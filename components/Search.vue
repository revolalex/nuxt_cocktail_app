<template>
<div class="mx-auto" style="width: 360px;">
  <b-form inline id="mySearch" @submit="onSubmit">
    <b-form-input
      size="sm"
      class="mr-sm-2"
      v-model="text"
      placeholder="Search a cocktail:"
    ></b-form-input>
    <b-button  size="sm" class="my-2 my-sm-0 mx-auto" type="submit" variant="info"
      >🍹Search</b-button
    ></b-form
  >
  </div>
</template>

<script>
export default {
  name: 'Search',
  data() {
    return {
      text: '',
    }
  },
  methods: {
    onSubmit(event) {
      event.preventDefault()
      this.$emit('searchClicked', this.text)
      this.text = ''
    },
  },
}
</script>

<style>
#mySearch {
  padding: 40px;
}
</style>