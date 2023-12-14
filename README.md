# demoComponentes

Es un exemple de com treballar amb components amb Vue 3. 

Hi ha un pare (App.vue) i 2 components fills. 
Els dos components fills son equivalents, la única diferència es que estan programats: 
- Fent servir Options API <script>
- Fent servir Composition API <script setup>

## Tipus de comunicacions
El pare passa informació (estructurada en js: objectes, arrays, variables ) als fills mitjançant props. 
Els fills es comuniquen amb els pares mitjançant emits avisant quan ha ocorregut un event i retornant informació. 
El pare injecta informació html als fills fent servir slots