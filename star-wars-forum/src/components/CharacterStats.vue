<template>
  <p>Favorite Percentage: {{ favoritePercentage.toFixed(2) }} {{ moreThanHalf }}</p>
  <p>Light Side Percentage: {{ lightSidePercentage.toFixed(2) }}</p>
  <p>Dark Side Percentage: {{ darkSidePercentage.toFixed(2) }}</p>
</template>

<script>
export default {
  props: {
    characters: {
      type: Array,
      required: true
    }
  },
  computed: {
        favoritePercentage() {
            return (this.characters.filter((char) => char.favorite).length / this.characters.length);
        },
        moreThanHalf() {
            return this.favoritePercentage >= 0.5 ? 'WOWW' : '';
        },
        lightSidePercentage() {
            return (this.characters.filter((char) => char.side === 'light').length /
                this.characters.length);
        },
        darkSidePercentage() {
            return (this.characters.filter((char) => char.side === 'dark').length /
                this.characters.length);
        }
    },
}</script>