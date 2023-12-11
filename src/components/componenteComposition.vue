<template>
  <div>
    Has pulsado {{ contadorPulsaciones }} veces<br>
    <button v-for="item in vector" :key="item" @click="pulsarBoton(item)">
      {{ item }}
    </button>
  </div>
</template>

<script setup>

import { ref } from 'vue';

const props = defineProps(['vector'])

const emit = defineEmits(['botonPulsado']);

const contadorPulsaciones = ref(0);

function pulsarBoton (texto) {
  contadorPulsaciones.value++;
  emit("botonPulsado", texto);
};
</script>

<style lang="scss" scoped>

</style>