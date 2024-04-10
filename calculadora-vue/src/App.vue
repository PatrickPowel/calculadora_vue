<template>
  <div class="calculator">
    <label for="num1">Número 1:</label>
    <input type="number" v-model.number="num1" @input="calcular">
    
    <label for="num2">Número 2:</label>
    <input type="number" v-model.number="num2" @input="calcular">
    
    <label for="operacao">Operação:</label>
    <select v-model="operacao" @change="calcular">
      <option value="+">Adição</option>
      <option value="-">Subtração</option>
      <option value="*">Multiplicação</option>
      <option value="/">Divisão</option>
    </select>
    
    <label for="resultado">Resultado:</label>
    <input type="text" v-model="resultado" readonly>
  </div>
</template>

<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operacao: '+',
      resultado: 0
    };
  },
  methods: {
    calcular() {
      switch (this.operacao) {
        case '+':
          this.resultado = this.num1 + this.num2;
          break;
        case '-':
          this.resultado = this.num1 - this.num2;
          break;
        case '*':
          this.resultado = this.num1 * this.num2;
          break;
        case '/':
          this.resultado = this.num1 / this.num2;
          break;
        default:
          this.resultado = 0;
      }
    }
  }
};
</script>

<style>
.calculator {
  margin: 20px;
}
input[type="number"], select {
  margin-bottom: 10px;
  padding: 5px;
}
input[type="text"] {
  font-weight: bold;
  padding: 5px;
}
</style>
