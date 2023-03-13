<template>
  <main>
    <div class="wrapper p-6 flex flex-col items-center md:flex-row md:flex-wrap md:gap-2 md:justify-center">
      <h1 class="text-2xl font-bold text-green-400 pb-4 md:w-full md:ml-12">{{ title }}</h1>

      <Villagers v-for="(villager) in villagers"
                 :id="villager['id']"
                 :key="villager['id']"
                 :birthday="villager['birthday-string']"
                 :imageUri="villager['image_uri']"
                 :name="villager['name']['name-USen']"
                 :personality="villager['personalityy']"

      />

    </div>
  </main>
</template>

<script>

import Villagers from "~/components/Villagers.vue";

export default {
  name: 'IndexPage',
  components: {Villagers},


  data() {
    return {
      villagers: [],
      title: "Liste des habitants :"
    }
  },

  async asyncData({$axios}) {
    const villagers = await $axios.$get('https://acnhapi.com/v1/villagers/');

    return {villagers}
  }
  
}
</script>
