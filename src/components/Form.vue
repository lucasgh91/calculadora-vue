<script setup>
  const props = defineProps(['valorUm', 'valorDois', 'operacao'])
</script>
<template>
  <div class="row">
    <form>
      <input type="number" @keyup="props.valorUm" class="form-control mt-2" placeholder="Digite o primeiro valor">
      <input type="number" @keyup="props.valorDois" class="form-control mt-2" placeholder="Digite o segundo valor">
      <select @change="props.operacao" class="form-control mt-3">
        <option value="adicao">Adição</option>
        <option value="subtracao">Subtração</option>
        <option value="divisao">Divisão</option>
        <option value="multiplicacao">Multiplicação</option>
      </select>
    </form>
  </div>
</template>