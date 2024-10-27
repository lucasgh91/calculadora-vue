<script setup>
  const props = defineProps(['valorUm', 'valorDois', 'resultado'])
</script>
<template>
  <div class="row mt-5">
    <h2 v-if="props.resultado">Resultado: {{ props.resultado }}</h2>
  </div>
</template>