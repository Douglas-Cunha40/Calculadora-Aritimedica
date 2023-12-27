<template>
    <div class="container">
      <input v-model.number="num1" @input="calcular" type="number" placeholder="Número 1">
      <select v-model="operacao" @change="calcular">
        <option value="+">+</option>
        <option value="-">-</option>
        <option value="*">*</option>
        <option value="/">/</option>
      </select>
      <input v-model.number="num2" @input="calcular" type="number" placeholder="Número 2">
      <div class="resultado">
        Resultado: {{ resultado }}
      </div>
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

<style scoped>
body {
  font-family: 'Arial', sans-serif;
  margin: 0;
  padding: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
}

input,
select {
  margin: 10px;
  padding: 10px;
  font-size: 1.2rem;
  border: 1px solid #ff2222;
  border-radius: 5px;
}

.resultado {
  margin-top: 20px;
  font-size: 1.5rem;
  font-weight: bold;
}
</style>

