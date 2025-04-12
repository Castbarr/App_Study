<template>
    <q-page class="q-pa-md flex flex-center">
        <div class="q-gutter-sm flex flex-center">
            <q-card class="responsive-card">
                <q-card-section>
                    <div class="text-h4 text-weight-bold text-center">Hardware: Componentes Internos</div>
                </q-card-section>

                <q-card-section>
                        <q-card-section>
                            <p class="text-h6">
                                El Procesador(CPU)
                            </p>
                        </q-card-section>
                        <q-card-section class="row items-start items-stretch q-col-gutter-md q-row-gutter-md">
                          <p class="col-12 col-md-7 text-justify q-pr-md">
                            El procesador, conocido como CPU (Unidad Central de Procesamiento), es como el cerebro de una computadora. Su tarea principal es procesar las instrucciones y coordinar todo el trabajo que realiza el sistema.<br><br>
                            Por ejemplo, cuando ejecutas un programa o navegas por internet, el procesador trabaja intensamente para interpretar las órdenes y mantener las operaciones en marcha. Se le puede comparar con un chef que maneja múltiples recetas al mismo tiempo, organizando ingredientes (datos) y asegurándose de que todo quede listo a tiempo.<br><br>
                            En resumen, el CPU es el componente encargado de tomar decisiones y distribuir el trabajo de manera eficiente en tu computadora.
                          </p>
                          <q-img
                          class="col-12 col-md-4 self-center rounded-borders"
                          src="assets/cpu.png"
                          style="max-height: 300px; max-width: 300px; object-fit: contain;"
                          />
                          <q-btn
                          class="blink q-ma-md q-pa-sm self-center"
                          round
                          color="secondary"
                          icon="add"
                          @click="mostrarMensaje"
                          />
                          <q-btn
                          class="blink q-ma-md q-pa-sm self-center"
                          color="secondary"
                          label="Video"
                          icon="play_circle"
                          @click="mostrarVideo"
                          />
                          <q-btn
                          class="blink q-ma-md q-pa-sm self-center"
                          color="secondary"
                          label="Partes del Procesador"
                          icon="list"
                          @click="partesDelProcesador"
                          />
        <q-dialog v-model="dialogoAbierto" persistent>
            <q-card style="max-width: 90vw; max-height: 90vh;">
                <q-card-section>
                    <div class="text-h6 text-weight-bold">Video: Procesador(CPU)</div>
                </q-card-section>
                <q-card-section class="q-pa-none">
                    <iframe 
                    width="560" height="315" 
                    src="https://www.youtube.com/embed/Wquylz_un6w?si=FY3Yjr8rMjtDBVpH" 
                    title="YouTube video player" frameborder="0" allow="accelerometer; 
                    autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; 
                    web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
                </q-card-section>
                <q-card-actions align="right">
                    <q-btn flat label="Cerrar" color="primary" @click="dialogoAbierto = false" />
                </q-card-actions>
            </q-card>
        </q-dialog>
                        </q-card-section>
                </q-card-section>
            </q-card>
        </div>
    </q-page>
</template>

<script setup>
import { useQuasar } from 'quasar';
import { ref } from 'vue';

const dialogoAbierto = ref(false);
const $q = useQuasar();
const mostrarMensaje = () => {
  $q.dialog({
    title: 'Información',
    html:true,
    message: "El encapsulado del procesador, es decir, la parte visible físicamente, suele medir entre 2 y 7 centímetros cuadrados, dependiendo del dispositivo en el que se utilice.",
    ok: {
      icon:'check',
      label: '',
      class: 'q-btn--rounded',
      flat: true,
    },
    style:'width: 500px; max-width: 90vw;'
  });
};
const partesDelProcesador = () => {
  $q.dialog({
    html:true,
    title: '<div style="display: flex; justify-content: center; align-items: center; background-color: #c6feb5; border-radius: 50%; width: 50px; height: 50px; margin: 0 auto;" translate="no">\
              <i class="q-icon material-icons" style="color: #006cff; font-size: 34px;" translate="no">priority_high</i>\
            </div>',
    message: 
    "<ul>\
        <li><strong>Unidad de Control (CU):</strong><br> Es la parte responsable de dirigir y coordinar todas las operaciones del CPU. Traduce las instrucciones de los programas en señales que controlan las demás partes del procesador.</li>\
        <li><strong>Unidad Aritmético-Lógica (ALU):</strong><br> Realiza operaciones matemáticas (como suma y resta) y lógicas (como comparaciones). Es fundamental para realizar cálculos y tomar decisiones básicas.</li>\
        <li><strong>Registros:</strong><br> Son pequeñas áreas de almacenamiento dentro del CPU. Guardan datos e instrucciones temporales para que el procesador pueda acceder a ellos rápidamente durante las operaciones.</li>\
        <li><strong>Cache:</strong><br> Una memoria de acceso rápido que guarda información frecuente o recientemente utilizada. Ayuda a acelerar el procesamiento al reducir el tiempo de acceso a datos.</li>\
        <li><strong>Buses:</strong><br> Son líneas de comunicación que transportan datos, direcciones y señales de control entre las distintas partes del CPU y hacia otros componentes de la computadora, como la memoria.</li>\
        <li><strong>Decodificador de instrucciones:</strong><br> Interpreta las instrucciones que vienen del programa y las traduce para que puedan ser ejecutadas por la ALU y otras unidades.</li>\
        <li><strong>Reloj (Clock):</strong><br> Genera pulsos eléctricos que sincronizan las operaciones del CPU. La velocidad del reloj determina qué tan rápido puede ejecutar instrucciones.</li>\
     </ul>\
    ",
    ok: {
      icon:"check",
      label: '',
      class: 'q-btn--rounded',
      flat: true,
    },
    style:'width: 500px; max-width: 90vw;'
  });
};

const mostrarVideo = () => {
    dialogoAbierto.value = true;
};
</script>

<style scoped>
@keyframes blink {
  0%, 100% { opacity: 1; }
  50% { opacity: 0.3; }
}

.blink {
  animation: blink 3s infinite;
}
iframe {
    border-radius: 8px;
}
</style>