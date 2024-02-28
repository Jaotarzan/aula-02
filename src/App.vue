<script setup>
import { ref } from 'vue'

const nome = 'João'
const idade = 16  
const contador = ref(0)

function inverter(txt) {
  return txt.split('').reverse().join('').toUpperCase()
}

function saudacao() {
  return alert('olá')
}

function decrementar() {
  if (contador.value > 0) contador.value--
}
</script>

<template>
<div class="info">
  <h1>Exemplo 1 - mostrando informações da tela</h1>
  <p>nome: {{ nome }}</p>
  <p>idade: {{ idade }}</p>
  <hr />
  <p>Para completar 50 anos faltam: {{ 50 - idade }}</p>
  <p>O nome tem {{ nome.length }} caracteres</p>
  <p>O nome invertido é {{ inverter(nome) }}</p>
  <hr />
  <p>exemplo da saudação</p>
  <button @click="saudacao">saudacao</button>
</div>

<div class="contador">
  <h1>Contador</h1>
  <p>contando: {{ contador }}</p>
  <hr />
  <button @click="contador++">+</button>
  <button @click="decrementar">-</button>
  <button @click="contador=0">0</button>
  <hr />
  <div id="menor" v-show="contador <= 10"> 
    <p>O valor é menor que 10</p>
  </div>
  <div id="maior" v-if="contador>10">
    <p>o valor é maior que 10</p>
  </div>
</div>
</template>

<style scoped>
.info, .contador {
  background-color: rgba(35,12,22,1);
  padding: 20px 30px;
  color: rgb(183, 210, 219);
  border-radius: 10px;
  margin-left: 5%;
}

h1 {
  color: white;
  font-weight: bold;
  font-size: 1.5em;
}

button {
  border: 1px solid black;
  border-radius: 7px;
  background-color: pink;
  margin: 1%;
}

#menor {
  background-color: red;
  color: white;
  margin: 2%;
  font-size: 1.5em;
}

#maior {
  background-color: green;
  color: white;
  margin: 2%;
  font-size: 1.5em;
}
</style>
