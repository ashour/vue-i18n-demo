<template>
  <div class="card">
    <h3>{{ title }}</h3>

    <img :src="imgUrl" />

    <p>Added {{ addedOn }}</p>
  </div>
</template>

<script>
export default {
  props: {
    id: Number,
    title: String,
    imgUrl: String,
    addedOn: String
  }
}
</script>

<style scoped>
.card {
  width: 30%;
  border: 1px solid #ccc;
}

.card img {
  width: 100%;
}
</style>
