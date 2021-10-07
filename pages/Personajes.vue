<template>
  <div class="mt-2">
    <v-row>
      <v-col></v-col>
      <v-col align="center" cols="3">
        <h1 class="characterListTitle">Personajes</h1>
      </v-col>
      <v-col></v-col>
    </v-row>
    <v-row>
      <v-col v-for="character in characters" :key="character.id" xl="4">
        <v-card class="rounded-xl">
          <v-img class="mx-auto" :src="character.imagen" width="200px" />
          <v-card-title class="justify-center">{{
            character.nombre
          }}</v-card-title>
        </v-card>
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  computed: {
    characters() {
      return this.$store.state.characterModule.characters
    },
  },
}
</script>

<style scoped>
.characterListTitle {
  font-size: 45px;
  font-family: 'GetSchwifty';
}
</style>
