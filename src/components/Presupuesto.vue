<script setup>
import { ref } from 'vue';

import Alerta from './Alerta.vue';

const presupuesto = ref(0);

const error = ref('');

const emit = defineEmits(['definir-presupuesto']);

const definirPresupuesto = () => {
  if (presupuesto.value <= 0) { 
    error.value = 'El presupuesto no es valido';

        setTimeout(() => {
          error.value = '';
        }, 3000);
    }

    emit('definir-presupuesto', presupuesto.value);
}

const validarPresupuesto = (event) => {
  const value = event.target.value;
  // Remueve cualquier carácter que no sea un número o un punto decimal
  event.target.value = value.replace(/[^\d.]/g, '');
  // Actualiza el valor del presupuesto
  presupuesto.value = event.target.value;
};

</script>

<template>
    <form 
        class="presupuesto"
        @submit.prevent="definirPresupuesto"
        >
        <Alerta v-if="error">
            {{ error }}
        </Alerta>
        <div class="campo">
            <label for="nuevo-presupuesto">Definir Presupuesto</label>
            <input 
                type="number" 
                id="nuevo-presupuesto" 
                class="nuevo-presupuesto"
                placeholder="Agrega tu presupuesto" 
                required
                min="0"
                v-model="presupuesto"
                @input="validarPresupuesto"
            >
        </div>
        <input type="submit" value="Definir Presupuesto">
    </form>
</template>

<style scoped>
    .presupuesto {
        width: 100%;
    }
    .campo {
        display: grid;
        gap: 2rem;
    }

    .presupuesto label {
        font-size: 2.1rem;
        text-align: center;
        color: var(--azul);
    }
    .presupuesto input[type="number"] {
        background-color: rgba(179, 179, 180, 0.533);
        border: none;
        border-radius: 1rem;
        width: 100%;
        padding: 1rem;
        text-align: center;
        font-size: 2.2rem;
    }

    .presupuesto input[type="submit"] {
        background-color: var(--azul);
        border: none;
        border-radius: 1rem;
        padding: 1rem;
        text-align: center;
        font-size: 2rem;
        margin-top: 2rem;
        color: var(--blanco);
        font-size: 2.2rem;
        font-weight: 900;
        width: 100%;
        transition: background-color 0.6s ease;
    }

    .presupuesto input[type="submit"]:hover {
        background-color: #1048A4;
        cursor: pointer;
    }
</style>
