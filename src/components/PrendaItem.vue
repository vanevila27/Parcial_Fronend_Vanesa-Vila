<!-- src/components/ListaItems.vue -->
<template>
  <div class="lista">
    <h3>Catalogo de Prendas (contador general: {{ }})</h3>
    
  </div>
</template>

<script setup>
import { ref, watch } from 'vue'



// Array de tarjetas, cada una con su nombre y sus colores
const items = ref([
  { nombre: 'Camisa Clasica(M)', vecesElegida: 0 },
  { nombre: 'Pantalon Carlo (L)', vecesElegida: 0 },
  { nombre: 'Vestido Veraniego (S)', vecesElegida: 0 },
  { nombre: 'Chaqueta Danim (XL)', vecesElegida: 0 }
  { nombre: 'Jersey de Lana (M)', vecesElegida: 0 }
  { nombre: 'Short Deportivo (S)', vecesElegida: 0 }
])

// Índice del elemento seleccionado
const seleccionadoIndex = ref(null)

// Cada vez que cambia el contador, se elige una fruta al azar y se incrementa su contador
watch(
  () => props.boton,
  () => {
    const randomIndex = Math.floor(Math.random() * items.value.length)
    seleccionadoIndex.value = randomIndex
    items.value[randomIndex].vecesElegida++
  }
)
</script>

<style>
.lista {
  margin-top: 20px;
}

ul {
  list-style: none;
  padding: 0;
}

li {
  background-color: #f3f3f3;
  margin: 5px;
  padding: 8px;
  border-radius: 5px;
  transition: 0.3s;
  text-align: left;
}

/* Tarjeta seleccionada visualmente */
.seleccionado {
  background-color: #ffeb3b;
  font-weight: bold;
  transform: scale(1.05);
}
</style>
