<script setup>
  import Formulario from './components/Formulario.vue';
  import Clima from './components/Clima.vue';
  import Spinner from './components/Spinner.vue';
  import useClima from './composables/useClima';
  import Alerta from './components/Alerta.vue';

  const { obtenerClima, clima, mostarClima, cargando, error } = useClima()

  console.log()

;
</script>

<template>
  <h1 class="titulo">Buscador de Clima</h1>
  <div class="contenedor buscador-clima">
    <Formulario
      @obtener-clima="obtenerClima"
    />

    <Spinner v-if="cargando"/>
    <Alerta v-if="error">{{ error }}</Alerta>

    <Clima 
      v-if="mostarClima"
      :clima="clima"
    />
  </div>
</template>

