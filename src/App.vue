<template>
  <div class="container">
    <header>
      <h1>Calculadora Aritmética</h1>
      <p>Escolha entre soma ou subtração:</p>
    </header>
    <form>
      <select v-model="operacao" class="form-control">
        <option value="soma">Soma</option>
        <option value="subtracao">Subtração</option>
      </select>
      <input
        v-model="estado.numeroA"
        type="number"
        placeholder="Digite o primeiro número"
        class="form-control"
      />
      <input
        v-model="estado.numeroB"
        type="number"
        placeholder="Digite o segundo número"
        class="form-control"
      />
      <label>Seu resultado é: {{ calcularResultado() }}</label>
    </form>
  </div>
</template>

<script setup>
import { reactive } from "vue";

const estado = reactive({
  numeroA: 0,
  numeroB: 0,
});

let operacao = "soma";

const calcularResultado = () => {
  return operacao === "soma" ? estado.numeroA + estado.numeroB : estado.numeroA - estado.numeroB;
};
</script>

<style scoped></style>
