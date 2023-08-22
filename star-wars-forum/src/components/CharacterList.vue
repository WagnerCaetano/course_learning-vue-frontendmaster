<script>
export default {
  props: {
    characters: {
      type: Array,
      required: true
    }
  },
  methods: {
    toggleFavorite(character) {
      this.characters.find((char) => char.name === character.name).favorite =
        !this.characters.find((char) => char.name === character.name).favorite
    },
    deleteChar(character) {
      this.characters.splice(this.characters.indexOf(character), 1);
    }
  }
}</script>

<template>
  <table>
    <tr>
      <th>Name</th>
      <th>Side</th>
      <th>Favorite?</th>
      <th>Actions</th>
    </tr>
    <tr v-if="characters.length > 0" v-for="character in characters">
      <td>{{ character.name }}</td>
      <td>{{ character.side }}</td>
      <td>{{ character.favorite }}</td>
      <td><button v-on:click="toggleFavorite(character)">Favorite</button><button v-on:click="deleteChar(character)">Delete</button></td>
    </tr>
    <tr v-else>
      <td colspan="2">No characters found</td>
    </tr>
  </table>
</template>