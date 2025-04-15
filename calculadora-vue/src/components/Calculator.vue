<template>
    <div class="calculator">
      <h2>Calculadora</h2>
      <div class="display">Has clicat: {{ selectedNumber || '---' }}</div>
      <div class="keyboard">
        <button 
          v-for="num in numbers" 
          :key="num" 
          @click="selectNumber(num)"
          class="number-btn"
        >
          {{ num }}
        </button>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'CalculatorDisplay',
    data() {
      return {
        selectedNumber: null,
        numbers: [1, 2, 3, 4, 5, 6, 7, 8, 9]
      }
    },
    methods: {
      selectNumber(num) {
        this.selectedNumber = num
        console.log(`Número seleccionat: ${num}`)
      }
    }
  }
  </script>
  
  <style scoped>
  .calculator {
    max-width: 300px;
    margin: 20px auto;
    padding: 20px;
    border: 1px solid #42b983;
    border-radius: 10px;
    text-align: center;
  }
  
  .display {
    margin: 20px 0;
    padding: 10px;
    background: #f5f5f5;
    border-radius: 5px;
    font-size: 1.2em;
    min-height: 20px;
  }
  
  .keyboard {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 10px;
  }
  
  .number-btn {
    padding: 15px;
    font-size: 1.2em;
    border: none;
    border-radius: 5px;
    background: #42b983;
    color: white;
    cursor: pointer;
  }
  
  .number-btn:hover {
    background: #369f6b;
  }
  </style>