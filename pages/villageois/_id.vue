<template>
  <main>
    <div
      class="wrapper p-6 flex flex-col items-center md:flex-row md:flex-wrap md:gap-2 md:justify-center md:items-start">
      <ul class="pt-2">
        <li class="px-2">
          <AnimalDescription :text="villager.id" title="id"/>
        </li>
        <li class="px-2">
          <AnimalDescription :text="villager.name['name-USen']" title="Nom"/>
        </li>
        <li class="px-2">
          <AnimalDescription :text="villager.personality" title="Personalité"/>
        </li>
        <li class="px-2">
          <AnimalDescription :text="villager.birthday" title="Anniversaire"/>
        </li>
        <li class="px-2">
          <AnimalDescription :text="villager.species" title="Espèce"/>
        </li>
        <li class="px-2">
          <AnimalDescription :text="villager.gender" title="Genre"/>
        </li>
        <li class="px-2">
          <AnimalDescription :text="villager.hobby" title="Hobby"/>
        </li>
        <li class="px-2 pt-2">
          <NuxtLink
            class="bg-green-400 p-2 rounded text-white hover:bg-white hover:text-green-400 ease-in-out duration-300"
            to="/">
            Back
          </NuxtLink>
        </li>


      </ul>
      <div class="py-2">
        <ImageComponent :alt="name" :image-url="villager.image_uri"/>
      </div>
    </div>

  </main>
</template>

<script>
import AnimalDescription from "~/components/AnimalDescription.vue";
import ImageComponent from "~/components/ImageComponent.vue";

export default {
  name: "_id",
  components: {ImageComponent, AnimalDescription},

  async asyncData({params}) {
    const villager = await fetch(
      `https://acnhapi.com/v1/villagers/${params.id}`
    ).then((res) => res.json())
    return {villager}
  }

}


</script>

<style scoped>

</style>
