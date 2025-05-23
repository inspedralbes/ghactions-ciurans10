<template>
  <div class="keypad">
    <button v-for="number in numbers" :key="number" @click="emitClick(number)">
      {{ number }}
    </button>
  </div>
</template>

<script>
export default {
  name: 'CalculatorKeypad',
  data() {
    return {
      numbers: [1, 2, 3, 4, 5, 6, 7, 8, 9]
    };
  },
  methods: {
    emitClick(number) {
      // Emitimos un evento 'number-clicked' con el número como payload
      this.$emit('number-clicked', number);
    }
  }
};
</script>

<style scoped>
/* Las estilos con 'scoped' solo afectan a este componente */
.keypad {
  display: grid;
  grid-template-columns: repeat(3, 80px);
  gap: 10px;
  width: 260px;
  margin: 20px auto;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 8px;
  background-color: #f0f0f0;
}

.keypad button {
  width: 80px;
  height: 80px;
  font-size: 1.5em;
  border: none;
  border-radius: 5px;
  background-color: #e0e0e0;
  cursor: pointer;
  transition: background-color 0.2s;
}

.keypad button:hover {
  background-color: #d0d0d0;
}
</style>