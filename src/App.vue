<script setup>
const name = 'Vue dinámico'
const listener = "Listener Evento"
const arrayColores = ["blue", "red", "peru"]
const activo = true

// metodo = methods
const handleClick = () => {
  console.log("Me diste click")
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
</template>

<style>
h1 {
  color: red;
}
</style>