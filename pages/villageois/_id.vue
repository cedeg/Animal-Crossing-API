<template>
  <main>
    <div class="wrapper p-6 flex flex-col items-center md:flex-row md:flex-wrap md:gap-2 md:justify-center">
      <ul>
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
        <li class="py-2">
          <ImageComponent :alt="name" :image-url="villager.image_uri"/>
        </li>

      </ul>
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
