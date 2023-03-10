<template>
  <main>
    <div>
      <h1>MAIN</h1>
      
      <div v-for="villager in villagers">{{ villager.name['name-USen'] }}</div>
    </div>
  </main>
</template>

<script>


export default {
  name: 'IndexPage',


  data() {
    return {
      villagers: []
    }
  },

  async asyncData({$axios}) {
    const villagers = await $axios.$get('https://acnhapi.com/v1/villagers/')
    return {villagers}
  }


}
</script>
