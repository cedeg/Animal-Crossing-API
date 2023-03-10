<template>
  <div>
    <ul>
      <li>
        <p>Nom : {{ name }}</p>
      </li>
      <li>
        <p>Personnalité : {{ personality }}</p>
      </li>
      <li>
        <p>Anniversaire: {{ birthday }}</p>
      </li>
      <li>
        <p>{{ imageUri }}</p>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Villagers",
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
