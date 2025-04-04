<template>
  <q-page class="flex flex-center">
    <div style="position: absolute; top: 20px; left: 10px; color: white; font-size: 0.9rem;">
      <q-item-label><q-icon name="arrow_back"/>Click en los Modulos para comenzar</q-item-label>
    </div>
    <ul class="text-h6 q-pa-md">
      <h5 class="text-h6 q-ma-md">Contenido</h5>
      <li>Modulo 1. Introducción a la Computación</li>
      <li>Modulo 2. Funcionamiento interno de una Computadora</li>
      <li>Modulo 3. Internet y la Web</li>
      <li>Modulo 4. Conceptos emergentes y de actualidad</li>
    </ul>
    <div class="q-ma-md column">
      <q-btn
      class="q-mb-md"
      color="warning"
      label="¡Importante!"
      @click="mostrarMensaje"
      />
      <q-btn
      color="info"
      label="Sobre el Curso"
      @click="mostrarInfo"
      />
    </div>
  </q-page>
</template>

<script setup>
import { useQuasar } from 'quasar';
const $q = useQuasar();
const mostrarMensaje = () => {
  $q.dialog({
    title: 'Aviso',
    message: "El contenido de este curso refleja los conocimientos y perspectivas personales del autor.\
              No constituye una fuente oficial ni académica,\
              y se recomienda realizar estudios adicionales para una comprensión más amplia.\
              En este curso no se enseña programación ni el manejo de ningún software, el curso se enfoca\
              en que el estudiante comprenda los conceptos primordiales de la computación, asi como su\
              teoría subyacente",
    ok: {
      icon:'check',
      label: '',
      class: 'q-btn--rounded',
      flat: true,
    },
  });
};
const mostrarInfo = () => {
  $q.dialog({
    title: 'Nota',
    message: "El contenido del curso está diseñado para que el estudiante comprenda, desde cero,\
    el funcionamiento de las computadoras, la web, el internet y toda la tecnología relacionada.\
    El objetivo es proporcionar una base sólida que permita al estudiante adentrarse con confianza en la rama de su interés,\
    ya sea programación, análisis de datos, inteligencia artificial, ciberseguridad u otras áreas. Con este fundamento,\
    se busca facilitar un aprendizaje más efectivo y profundo en disciplinas tecnológicas avanzadas.",
    ok: {
      icon:'check',
      label: '',
      class: 'q-btn--rounded',
      flat: true,
    },
  });
};
</script>
<style scoped>
  .q-page {
    background: url(../assets/Fondo.png) no-repeat center center;
    background-size: cover;
    height: 100vh;
  }

  .text-h6 {
    font-size: 1.25rem;
    font-weight: 700; /* Changed to bold */
    line-height: 1.6;
    color: #ffffff;
    text-shadow:
    -2px -2px 0 #000,  
     2px -2px 0 #000,  
    -2px  2px 0 #000,  
     2px  2px 0 #000;
  }
</style>
