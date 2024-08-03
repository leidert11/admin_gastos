<script setup>
    import imagen from '../assets/img/grafico.jpg'
</script>
<template>
    <div class="dos-columnas">
        <div class="contenedor-grafico">
            <img :src="imagen" alt="">
        </div>
        
        <div class="contenedor-presupuesto">
            <button class="reset-app">
                Resetear
            </button>
            <p><span>Presupuesto :</span>$ 0</p>
    
            <p><span>Disponible :</span>$ 0</p>
    
            <p><span>Gastado :</span>$ 0</p>
        </div>
    </div>
</template>


<style  scoped>

    .dos-columnas {
        display: flex;
        flex-direction: column;
    }
    .dos-columnas > :first-child {
        margin-bottom: 3rem;
    }

    @media (min-width: 768px) {
        .dos-columnas {
            flex-direction: row;
            gap: 4rem;
            align-items: center;
        }
        .dos-columnas > :first-child {
            margin-bottom: 0;
        }
    }

    .contenedor-presupuesto {
        width: 100%;
    }

    .reset-app {
        background-color: #DB2777;
        border: none;
        padding: 1rem;
        width: 100%;
        color: var(--blanco);
        font-size: 1.8rem;
        font-weight: 700;
        text-transform: uppercase;
        border-radius: .6rem;
        transition-property: background-color;
        transition-duration: .3s;
    }

    .reset-app:hover {
        cursor: pointer;
        background-color: #c11d67;
    }
    .contenedor-presupuesto p {
        font-size: 2.3rem;
        text-align: center;
        color: var(--gris-oscuro);
    }
    @media (min-width: 768px) {
        .contenedor-presupuesto p {
            text-align: left;
        }
        
    }
    .contenedor-presupuesto span {
        font-weight: 900;
        color: var(--azul);
    }
</style>