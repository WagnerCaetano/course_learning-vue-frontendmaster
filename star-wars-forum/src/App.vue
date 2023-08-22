
<template>
  <CharacterManager @addCharacter="addCharacter" />
  <hr />
  <CharacterList :characters="listOfCharacters" />
  <hr />
  <CharacterStats :characters="listOfCharacters" />
  
</template>

<script>
import CharacterManager from './components/CharacterManager.vue'
import CharacterList from './components/CharacterList.vue'
import CharacterStats from './components/CharacterStats.vue'

export default {
    data() {
        return {
            listOfCharacters: [
                {
                    name: 'Luke',
                    side: 'light',
                    favorite: false
                },
                {
                    name: 'Darth Vader',
                    side: 'dark',
                    favorite: false
                },
                {
                    name: 'Yoda',
                    side: 'light',
                    favorite: false
                },
                {
                    name: 'Palpatine',
                    side: 'dark',
                    favorite: false
                }
            ]
        };
    },
    methods: {
        addCharacter(newCharacter) {
            this.listOfCharacters.push(newCharacter);
        }
    },
    components: { CharacterList, CharacterStats, CharacterManager }
}
</script>

<style scoped>
div,
p,
ul,
li {
  margin: 0;
  padding: 0;
}

th,
td {
  padding: 0.5rem;
}
</style>
