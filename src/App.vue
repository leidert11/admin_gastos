<script setup>
import { ref } from 'vue';
import Filtro from './components/Filtro.vue';
import Presupuesto from './components/Presupuesto.vue';

const presupuesto = ref(0);

const definirPresupuesto = (cantidad) => {

  presupuesto.value = cantidad;
};
</script>

<template>
  <div>
    <header>
      <h1>Planificador de Gastos</h1>
      <div class="contenedor-header contenedor sombra">

        <Presupuesto 
          v-if="presupuesto === 0"
          @definir-presupuesto="definirPresupuesto"
        />
        <p v-else>Presupuesto valido</p>
      </div>
    </header>
  </div>
</template>

<style>

  :root {
    --azul: #3b82f6;
    --blanco: #fff;
    --gris-claro: #94a3b8;
    --gris: #94a3b8;
    --gris-oscuro: #64748b;
    --negro: #000;
    --rojo: #B91C1C;
  }
  html {
    font-size: 62.5%;
    box-sizing: border-box;
    background-color: var(--blanco);
  }

  *, *:before, *:after {
    box-sizing: inherit;
  }

  body {
    font-size: 1.6rem;
    font-family: 'Lato', sans-serif;
    background-color: var(--gris-claro);
  }

  h1 {
    font-size: 4rem;
  }

  h2 {
    font-size: 3.2rem;
  }
  header{
    background-color: var(--azul);
  }
  header h1 {
    padding: 3rem 0;
    margin: 0;
    color: var(--blanco);
    text-align: center;
  }

  .contenedor {
    max-width: 120rem;
    margin: 0 auto;
    width: 90%;
  }
  .contenedor-header {
    padding: 5rem;
    margin-top: -5rem;
    transform: translateY(5rem);
  } 
    .sombra {
    -webkit-box-shadow: 0px 5px 15px 0px rgba(112,112,112,1);
    -moz-box-shadow: 0px 5px 15px 0px rgba(112,112,112,1);
    box-shadow: 0px 5px 15px 0px rgba(112,112,112,1);
    background-color: var(--blanco);
    border-radius: 1rem;
    padding: 2rem;
  } 
</style>
