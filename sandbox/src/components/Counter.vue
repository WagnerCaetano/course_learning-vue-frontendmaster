<script>
export default {
  data: () => ({
    count: 10,
    incrementAmount: 1,
  }),
  computed: {
    displayCounterTitle() {
      if (this.count % 2 === 0) {
        return 'Counter Even'
      }
      return 'Counter Odd'
    }
  },
  methods: {
    incrementCounter() {
      this.count += this.incrementAmount
    }
  }

}</script>

<template>
  <h1>{{ displayCounterTitle }}</h1>
  <p>{{ count }}</p>
  <button v-on:click="incrementCounter">Increment Count</button>
  <div>
    <label for="incrementAmount">Increment by:</label>
    <input type="number" v-model="incrementAmount" />
  </div>
</template>

<style scoped>
div,
p,
ul,
li {
  margin: 0;
  padding: 0;
}
</style>