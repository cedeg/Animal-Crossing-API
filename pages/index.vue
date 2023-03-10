<template>
  <main>
    <div class="wrapper p-6 flex flex-col items-center">
      <h1 class="text-2xl font-bold text-green-400 pb-4">{{ title }}</h1>

      <Villagers v-for="(villager, key) in villagers" :key="key" :birthday="villager['birthday-string']"
                 :imageUri="villager['image_uri']"
                 :name="villager['name']['name-USen']"
                 :personality="villager['personality']"

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

  /*activated() {
    if (this.$fetchState.timestamp <= Date.now() - 60000) {
      this.$fetch();
    }
  },
*/
  async asyncData({$axios}) {
    const villagers = await $axios.$get('https://acnhapi.com/v1/villagers/');

    return {villagers}
  }

  /*  async fetch() {
      this.villagers = await fetch('https://acnhapi.com/v1/villagers/').then((res) => res.json());
    }*/


}
</script>
