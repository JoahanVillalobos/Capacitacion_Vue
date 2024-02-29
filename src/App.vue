<script setup>
import { ref, computed } from 'vue'
const name = 'Vue dinámico'
const listener = "Listener Evento"
const arrayColores = ["blue", "red", "peru"]
const activo = true
const counter = ref(0)
const favNumber = ref([])

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

const classCounter = computed(() => {
  if (counter.value === 0) {
    return "zero";
  }
  return counter.value > 0 ? "positive" : "negative"
})

const favorite = computed(() => {
  const number = favNumber.value.find((num) => num === counter.value);
  return number || number === 0;
})

const addFavorite = () => {
  favNumber.value.push(counter.value)
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

  <h1 :style="`color: ${arrayColores[0]}`">Reactividad Practica</h1>
  <h2 :class="classCounter">{{ counter }}</h2>
  <button @:click="increment">Incrementar</button>
  <button @:click="decrement">Decrement</button>
  <button @:click="reset">Reset</button>
  <button :disabled="favorite" @:click="addFavorite">Favorite</button>
  <ul>
    <li v-for="(item, index) in favNumber" :key="index">
      {{ item }}
    </li>
  </ul>
</template>

<style>
h1 {
  color: red;
}

.positive {
  color: #23f323;
}

.negative {
  color: #ff0000;
}

.zero {
  color: #cd853f;
}
</style>