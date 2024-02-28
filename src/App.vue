<script setup>
const name = 'Vue dinámico'
const colorStyle = "color: blue"
const arrayColores = ["blue", "red", "peru"]
const activo = true
</script>

<template>
  <h1>Hola {{ name.toUpperCase() }}!</h1>
  <h2>{{ arrayColores }}</h2>
  <h2 :style="`color: ${arrayColores[0]}`">soy azul</h2>
  <h2 v-if="activo">Estoy activo</h2>
  <p v-else-if="!activo">Estoy inactivo</p>
  <p v-else>Estoy indeciso</p>

  <h2 v-show="activo">Estoy activo v-show</h2>
</template>

<style>
h1 {
  color: red;
}
</style>