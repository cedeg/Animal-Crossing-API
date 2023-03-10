<template>
  <img alt="alt" v-bind:src="imageUrl">
</template>

<script>
export default {
  name: "ImageComponent",
  props: {
    imageUrl: String,
    alt: String
  }
}
</script>

<style scoped>

</style>
