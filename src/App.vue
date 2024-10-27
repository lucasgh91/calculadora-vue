<script setup>
import { reactive } from 'vue';
import Form from './components/Form.vue'
import Header from './components/Header.vue'
import Resultado from './components/Resultado.vue'

const estado = reactive({
  valor1: undefined,
  valor2: undefined,
  operacao: 'adicao',
})

function resultado() {

  if (estado.valor1 === undefined || estado.valor2 === undefined) {
    return 0
  }

  switch (estado.operacao) {
    case 'adicao':
      return (estado.valor1 + estado.valor2)
      break;
    case 'subtracao':
      if ((estado.valor1 - estado.valor2) == 0)
        return '0'
      else
        return (estado.valor1 - estado.valor2)
      break;
    case 'divisao':
      if ((estado.valor1 / estado.valor2) == 0)
        return '0'
      else
        return (estado.valor1 / estado.valor2)
      break;
    case 'multiplicacao':
    if ((estado.valor1 * estado.valor2) == 0)
        return '0'
      else
        return (estado.valor1 * estado.valor2)
      break;
  }
}

</script>

<template>
  <div class="container">
    <Header />
    <Form :valor-um="evt => evt.target.value === '' ? estado.valor1 = 0 : estado.valor1 = parseFloat(evt.target.value)"
      :valor-dois="evt => evt.target.value === '' ? estado.valor2 = 0 : estado.valor2 = parseFloat(evt.target.value)"
      :operacao="evento => estado.operacao = evento.target.value" />
    <Resultado :valor-um="estado.valor1" :valor-dois="estado.valor2" :resultado="resultado()" />
  </div>
</template>

<style scoped></style>
