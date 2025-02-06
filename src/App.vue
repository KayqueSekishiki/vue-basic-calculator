<script setup>
import { ref, computed } from "vue";

const num1 = ref(0);
const num2 = ref(0);
const operacao = ref("+");

const resultado = computed(() => {
  switch (operacao.value) {
    case "+":
      return num1.value + num2.value;
    case "-":
      return num1.value - num2.value;
    case "*":
      return num1.value * num2.value;
    case "/":
      return num2.value !== 0
        ? num1.value / num2.value
        : "Impossível realizar divisão por 0";
    default:
      return 0;
  }
});
</script>

<template>
  <div class="calculator">
    <h2>Minha Calculadora com VUE</h2>
    <input type="number" v-model.number="num1" placeholder="Digite um número" />
    <select v-model="operacao">
      <option value="+">+</option>
      <option value="-">-</option>
      <option value="*">×</option>
      <option value="/">÷</option>
    </select>
    <input
      type="number"
      v-model.number="num2"
      placeholder="Digite outro número"
    />
    <h3>Resultado: {{ resultado }}</h3>
  </div>
</template>

<style scoped>
.calculator {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  background: white;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  text-align: center;
}

input,
select {
  margin: 10px;
  padding: 5px;
  font-size: 18px;
}

footer {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
</style>
