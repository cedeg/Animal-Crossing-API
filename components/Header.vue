<template>
  <header>
   <div class="bg-green-400 p-4 text-white text-center">
     <h1>{{ title }}</h1>
   </div>
  </header>
</template>

<script>
export default {
  name: "Header",

  data() {
    return {
      title: "Mon site sur Animal Crossing",
    }
  }
}
</script>

<style scoped>

</style>
