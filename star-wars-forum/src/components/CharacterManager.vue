<template>
  <h1>Star Wars</h1>
  <div style="display: flex; flex-direction: row; gap: 8px">
    <input type="text" name="name" v-model="newCharacter.name" />
    <select name="side" id="side" v-model="newCharacter.side">
      <option value="light">Light</option>
      <option value="dark">Dark</option>
    </select>

    <button @click="addCharacter">Add Character</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newCharacter: {},
    };
  },
  methods: {
    addCharacter() {
            this.newCharacter.favorite = false;
            this.$emit('addCharacter', this.newCharacter);
            this.newCharacter = {}
        }
  },
  emits: ['addCharacter'],
}</script>
