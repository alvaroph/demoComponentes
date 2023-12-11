<template>
    <div>
        Has pulsado {{ contadorPulsaciones }} veces<br>
        <button v-for="item in vector" :key="item" @click="pulsarBoton(item)">
      {{ item }}
    </button>
    </div>
</template>

<script>
export default {
  name: "componenteObjects",
  data() {
    return {
        contadorPulsaciones: 0
    };
  },
  props: {
    vector: {
      type: Array,
      required: true
    }
  },
  methods: {
    pulsarBoton(texto) {
      this.contadorPulsaciones++;
      this.$emit("botonPulsado", texto);
    }
  }
};
</script>

<style lang="scss" scoped>

</style>