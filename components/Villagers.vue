<template>
  <main>
    <ul>
      <!-- faire l'iD-->
      <li class="px-2">
        <AnimalDescription :text="name" title="Nom"/>
      </li>
      <li class="px-2">
        <AnimalDescription :text="personality" title="Personalité"/>
      </li>
      <li class="px-2">
        <AnimalDescription :text="birthday" title="Anniversaire"/>
      </li>
      <li class="px-2">
        <AnimalDescription :text="id" title="id"/>
      </li>
      <li class="py-2 relative ease-in-out duration-300 hover:scale-125">
        <NuxtLink :to="'/villageois/' + id" class="">
          <p class="absolute inset-1/3  opacity-50  text-xl text-white ">Voir
            plus</p>
          <ImageComponent :alt="name" :image-url="imageUri" class="rounded"/>
        </NuxtLink>

      </li>
    </ul>
  </main>


</template>

<script>
import AnimalDescription from "~/components/AnimalDescription.vue";
import ImageComponent from "~/components/ImageComponent.vue";

export default {

  name: "Villagers",
  components: {ImageComponent, AnimalDescription},
  props: {
    name: String,
    personality: String,
    birthday: String,
    imageUri: String,
    id: Number,

  }
}

</script>

<style scoped>

</style>
