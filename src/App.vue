<script setup>
import { ref } from 'vue'
const nome = 'Gustavo'
const idade = 16

function inverter(texto) {
  return texto.split('').reverse().join('')
}

function saudacao() {
  return `Olá, ${nome}!`
}


const contador = ref(0)

function incrementar() {
  contador.value++
}

function decrementar() {
  if (contador.value !== 0) {
    contador.value--
  }
}

function resetar() {
  contador.value = 0
}

</script>

<template>
  <main>
    <div class="info">
      <h1>Exemplo 1 - Mostrando informações na tela</h1>
      <p>Nome: {{ inverter(nome).toUpperCase() }}</p>
      <p>Idade: {{ idade }} anos</p>
      <hr />
      <p>Para completar 50 anos faltam: {{ 50 - idade }} anos</p>
      <p>O nome tem {{ nome.length }} caracteres</p>
      <p>O nome invertido é: {{ inverter(nome) }}</p>
      <hr />
      <p>Exemplo de saudação usando função</p>
      <p>{{ saudacao() }}</p>
    </div>
    <div class="info2">
      <h1>contador</h1>
    <p>Contador: {{ contador }}</p>
    <div class="botaos">
      <button @click="incrementar" class="botao1">+</button>
    <button @click="decrementar" class="botao1">-</button>
    <button @click="resetar" class="botao1">reset</button>
    </div>
    <div class="apareceu">
        <p v-if="contador > 10" style="background-color: green;">Número maior que 10</p>
        <p v-else-if="contador < 10" style="background-color: red;">Número menor que 10</p>
    </div>
    
    </div>
  </main>
</template>

<style scoped>
main {
  display: flex;
  gap: 50px;
  justify-content: center;
}
.info , .info2 {
  background-color: rgba(35, 12, 22, 1);
  padding: 20px 30px;
  color: rgb(183, 210, 219);
  border-radius: 10px;
}
.info2 {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
.botaos {
  display: flex;
  gap: 10px;
}
h1 {
  color: white;
  font-weight: bold;
  font-size: 1.5em;
}
</style>
