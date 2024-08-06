<template>
  <div id="app">
    <h1>Calculadora Aritmética</h1>
    <div class="calculator">
      <input type="number" v-model.number="number1" @input="calculate" placeholder="Número 1" />
      <select v-model="operation" @change="calculate">
        <option value="+">+</option>
        <option value="-">-</option>
        <option value="*">*</option>
        <option value="/">/</option>
      </select>
      <input type="number" v-model.number="number2" @input="calculate" placeholder="Número 2" />
      <p>Resultado: {{ result }}</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      number1: 0,
      number2: 0,
      operation: '+',
      result: 0
    };
  },
  methods: {
    calculate() {
      switch (this.operation) {
        case '+':
          this.result = this.number1 + this.number2;
          break;
        case '-':
          this.result = this.number1 - this.number2;
          break;
        case '*':
          this.result = this.number1 * this.number2;
          break;
        case '/':
          this.result = this.number1 / this.number2;
          break;
      }
    }
  },
  mounted() {
    this.calculate();
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  margin-top: 60px;
}

.calculator {
  display: flex;
  flex-direction: column;
  align-items: center;
}

input,
select {
  margin: 10px;
  padding: 10px;
  font-size: 16px;
}

p {
  font-size: 20px;
  font-weight: bold;
}
</style>
