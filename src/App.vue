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

    <componenteObjects :vector="datos" @botonPulsado="sacarMensaje">
      <h2>Component per objects</h2>
    </componenteObjects>

    <componenteComposition :vector="datos" @botonPulsado="sacarMensaje" >
      <h2>
        Component per Composition
      </h2>
      </componenteComposition>
  </div>
 
</template>

<style scoped>

</style>
