<script>
import Counter from './components/Counter.vue';
import BaseButton from './components/BaseButton.vue';

export default {
    data() {
        return {
            message: 'Hello it works',
            listOfNumbers: [1, 2, 3, 4, 5]
        };
    },
    components: { Counter, BaseButton }
}
</script>

<template>
  <Counter />

  <hr />

  <h1>Listing, IfElse, For</h1>
  <h3>If else logic:</h3>
  <p v-if="message.length % 2 === 0">Even: {{ message.toUpperCase() }}</p>
  <p v-else>Odd: {{ message }}</p>
  <h3>Number List:</h3>
  <ul>
    <li v-for="number in listOfNumbers" :key="`item-${index}`">number: {{ number }}</li>
  </ul>

  <hr>
  <BaseButton> Click me </BaseButton>
</template>


