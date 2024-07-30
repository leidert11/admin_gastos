<script setup>

</script>
<template>
    <div class="alerta">
        <slot></slot>
    </div>
</template>


<style scoped>
    .alerta {
        padding: 1rem;
        font-weight: 900;
        text-transform: uppercase;
        text-align: center;
        font-size: 1.5rem;
        background-color: var(--blanco);
        border-left: .5rem solid var(--rojo);
        color: var(--rojo);
        margin-bottom: 2rem;
    }

</style>