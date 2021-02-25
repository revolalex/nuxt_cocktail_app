<template>
  <div>
    <h1 class="neon">{{ titre }}</h1>
  </div>
</template>

<script>
export default {
  name: 'Titre',
  props: {
    titre: String,
  },
}
</script>

<style>
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
  font-size: 5rem;
  text-align: center;
}
</style>