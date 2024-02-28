<script setup>
const name = 'Vue dinámico'
const colorStyle = "color: blue"
</script>

<template>
  <h1>Hola {{ name.toUpperCase() }}!</h1>
  <h2 v-bind:style="colorStyle">soy azul</h2>
</template>

<style>
h1 {
  color: red;
}
</style>