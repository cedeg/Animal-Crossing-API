<template>
  <p><span class="font-bold"> {{ title }} : </span>{{ text }}</p>
</template>

<script>
export default {
  name: "AnimalDescription",
  props: {
    title: String,
    text: String
  }
}
</script>

<style scoped>

</style>
