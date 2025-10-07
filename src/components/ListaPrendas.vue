<!-- src/components/Contador.vue -->
<template>
  <div class="">
    <h2> <span :class="boton">{{ boton}}</span></h2>
    <button @click="Ordenar por Stock">Ordenar por Stock</button>

    <!-- Componente Nieto -->
    <ListaItems :="" />
  </div>
</template>
<script setup>
import { ref, computed } from 'vue'
import CatalogoManager from './CatalogoManager.vue'



// clase dinámica según el valor
const contadorClass = computed(() =>
  contador.value >= 10 ? 'contador-alto' : 'contador-normal'
)
</script>


button {
  background-color: #4caf50;
  color: white;
  border: none;
  padding: 8px 12px;
  border-radius: 8px;
  cursor: pointer;
}

.contador-alto {
  color: red;
  font-weight: bold;
}

.contador-normal {
  color: green;
}
</style>
<!--componente hijo-->



