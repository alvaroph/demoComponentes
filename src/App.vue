<script>
import componenteObjects from "./components/componenteObjects.vue";
import componenteComposition from "./components/componenteComposition.vue";

  export default {
    data() {
      return {
        inputText: '',
        datos: []
      };
    },
    methods: {
      addToVector() {
        this.datos.push(this.inputText);
        this.inputText = '';
      },
      sacarMensaje(texto) {
        alert(texto);
      }
    },
    components: {
      componenteObjects,componenteComposition
    }
  };
</script>


<template>
   <div>
    <input v-model="inputText" type="text" />
    <button @click="addToVector">Agregar</button>
    <ul>
      <li v-for="dato in datos" :key="dato">{{ dato }}</li>
    </ul> 
    <h1>Componente escrito en Objects</h1>
    <componenteObjects :vector="datos" @botonPulsado="sacarMensaje" />

    <h1>Componente escrito en Composition</h1>
    <componenteComposition :vector="datos" @botonPulsado="sacarMensaje" />
  </div>
 
</template>

<style scoped>

</style>
