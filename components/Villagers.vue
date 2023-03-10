<template>
  <div>
    <ul>
      <li class="px-2">
        <AnimalDescription :text="name" title="Nom"/>
      </li>
      <li class="px-2">
        <AnimalDescription :text="personality" title="Personalité"/>
      </li>
      <li class="px-2">
        <AnimalDescription :text="birthday" title="Anniversaire"/>
      </li>
      <li class="py-2">
        <ImageComponent :alt="name" :image-url="imageUri"/>
      </li>
    </ul>
  </div>
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
    imageUri: String

  }
}
</script>

<style scoped>

</style>
