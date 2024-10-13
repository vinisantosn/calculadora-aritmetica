<script setup>
import { reactive } from 'vue';
import Cabecalho from './components/Cabecalho.vue';
import Calculadora from './components/Calculadora.vue'

const estado = reactive({
  numeroA: 0,
  operacao: '+',
  numeroB: 0,
  resultado: null,
})

const setOperacao = () => {
  return estado.operacao
}
const getResultado = () => {
  const { numeroA, operacao, numeroB } = estado
  switch (operacao) {
    case '+':
      return parseInt(numeroA) + parseInt(numeroB);
    case '-':
      return parseInt(numeroA) - parseInt(numeroB);
    case '*':
      return parseInt(numeroA) * parseInt(numeroB);
    case '/':
      return parseInt(numeroA) / parseInt(numeroB);    
  }
  
}

</script>

<template>
  <div class="container">
    <Cabecalho />
    <Calculadora :seleciona-numero-a="estado.numeroA" :edita-num-a="evento => estado.numeroA = evento.target.value"
      :seleciona-operacao="evento => estado.operacao = evento.target.value" :seleciona-numero-b="estado.numeroB"
      :edita-num-b="evento => estado.numeroB = evento.target.value" 
      :resultado="getResultado()" />
  </div>
</template>

<style scoped></style>
