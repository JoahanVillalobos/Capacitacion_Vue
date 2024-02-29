<script setup>
import { ref } from 'vue'
const name = 'Vue dinámico'
const listener = "Listener Evento"
const arrayColores = ["blue", "red", "peru"]
const activo = true
const counter = ref(0)

// metodo = methods
const handleClick = () => {
  console.log("Me diste click")
}

const increment = () => {
  counter.value++
}
const decrement = () => {
  counter.value--
}
const reset = () => {
  counter.value = 0
}


</script>

<template>
  <h1>Hola {{ name.toUpperCase() }}!</h1>
  <h2>{{ arrayColores }}</h2>
  <h2 :style="`color: ${arrayColores[0]}`">soy azul</h2>
  <h2 v-if="activo">Estoy activo</h2>
  <p v-else-if="!activo">Estoy inactivo</p>
  <p v-else>Estoy indeciso</p>
  <h2 v-show="activo">Estoy activo v-show</h2>

  <h2 :style="`color: ${arrayColores[2]}`">{{ listener }}</h2>
  <button v-on:click="handleClick">Activame 1</button>
  <button @click="handleClick">Activame 2</button>

  <h1 :style="`color: ${arrayColores[1]}`">Reactividad Practica</h1>
  <h2 :class="counter > 0 ? 'positivo' : 'negativo'">{{ counter }}</h2>
  <button @:click="increment">Incrementar</button>
  <button @:click="decrement">Decrement</button>
  <button @:click="reset">Reset</button>
</template>

<style>
h1 {
  color: red;
}

.positivo {
  color: #23f323;
}

.negativo {
  color: #ff0000;
}
</style>