<template>
  <div id="app">
    <h1>Teclado de Calculadora</h1>
    <CalculatorKeypad @number-clicked="handleNumberClicked" />
    <p v-if="clickedNumber">Has clicado el número: <strong>{{ clickedNumber }}</strong></p>
  </div>
</template>

<script>

import CalculatorKeypad from './components/CalculatorKeypad.vue';

export default {
  name: 'App',
  components: {
    CalculatorKeypad 
  },
  data() {
    return {
      clickedNumber: null
    };
  },
  methods: {
    
    handleNumberClicked(number) {
      this.clickedNumber = number;
    }
  }
};
</script>

<style>

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>