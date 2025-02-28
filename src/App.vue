<script setup>
import { ref } from "vue";

const numeros = [1, 2, 3, 4, 5, 6, 7, 8, 9];
const mensaje = ref("");

const mostrarNumero = (num) => {
  mensaje.value = `Has clicat el número: ${num}`;
};
</script>

<template>
  <div class="calculadora">
    <div class="teclat">
      <button v-for="num in numeros" :key="num" @click="mostrarNumero(num)" class="tecla">
        {{ num }}
      </button>
    </div>
    <p v-if="mensaje" class="missatge">{{ mensaje }}</p>
  </div>
</template>

<style scoped>
.calculadora {
  text-align: center;
  font-family: Arial, sans-serif;
}

.teclat {
  display: grid;
  grid-template-columns: repeat(3, 60px);
  gap: 10px;
  justify-content: center;
  margin-top: 20px;
}

.tecla {
  width: 60px;
  height: 60px;
  font-size: 20px;
  font-weight: bold;
  cursor: pointer;
  border: 2px solid #ffffff;
  background-color: #000000;
  border-radius: 8px;
  transition: 0.2s;
}

.tecla:hover {
  background-color: #ddd;
}

.missatge {
  margin-top: 20px;
  font-size: 18px;
  font-weight: bold;
  color: #007bff;
}
</style>