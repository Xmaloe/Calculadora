<template>
    <div class="container">
      <div class="calculo">
        <input v-model="num1" type="number" class="form-control" @input="calcular" placeholder="Digite o número:" />
        <select v-model="operacao" class="form-select" @change="calcular">
            <option value="soma">+</option>
            <option value="subtracao">-</option>
            <option value="multiplicacao">x</option>
            <option value="divisao">/</option>
        </select>
        <input v-model="num2" type="number" class="form-control" @input="calcular" placeholder="Digite o número:" />
        <div class="result">Resultado: {{ resultado }}</div>
        </div>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        num1: '',
        num2: '',
        operacao: "soma",
      };
    },
    computed: {
      resultado() {
        const n1 = parseFloat(this.num1);
        const n2 = parseFloat(this.num2);

        switch (this.operacao) {
          case "soma":
            return n1 + n2;
          case "subtracao":
            return n1 - n2;
          case "multiplicacao":
            return n1 * n2;
          case "divisao":
            return n1 / n2;
          default:
            return 0;
        }
      },
    },
  };
</script>

<style scoped>
  .calculo {
  margin: 20px;
  padding: 20px;
  border: 3px solid #000;
  border-radius: 8px;
  background: #ccc;
}

input {
  border: 2px solid #000;
  font-weight: bold;
}

select {
  margin-top: 12px;
  margin-bottom: 12px;
}

.result {
  margin-top: 10px;
  font-weight: bold;
}
</style>