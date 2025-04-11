<template>
    <q-page class="q-pa-md flex flex-center">
        <div class="q-gutter-sm flex flex-center">
            <q-card class="responsive-card">
                <q-card-section>
                    <div class="text-h5 text-weight-bold text-center">Hardware: Componentes Internos</div>
                </q-card-section>

                <q-card-section>
                        <q-card-section>
                            <p class="text-h6">
                                La Memoria RAM
                            </p>
                        </q-card-section>
                        <q-card-section class="row items-start items-stretch q-col-gutter-md q-row-gutter-md">
                          <p class="col-12 col-md-7 text-justify q-pr-md">
                            La <strong>memoria RAM</strong> (Random Access Memory) es como la <strong>mesa de trabajo</strong> de tu computadora.<br><br>
                            Imagina que estás cocinando y tienes todos los ingredientes y utensilios listos sobre la mesa. Cuanto más grande sea la mesa, más cosas puedes tener a la mano sin necesidad de ir a la despensa a cada rato. <strong>La RAM hace lo mismo con la información que tu PC usa en ese momento</strong>: almacena temporalmente los datos y programas que estás ejecutando para que la computadora los acceda rápidamente, en lugar de ir a buscarlos al disco duro (que es mucho más lento).<br><br>
                            Cuando apagas la computadora, la información de la RAM desaparece, porque es una <strong>memoria volátil</strong>. Por eso, si no guardas un documento antes de apagar el equipo, lo pierdes.<br><br>
                            <strong>En resumen</strong>: La RAM es la memoria de trabajo de la computadora, donde se guardan temporalmente los datos y programas que estás usando para que funcionen rápido y sin interrupciones. Cuanta más RAM tengas, más programas podrás ejecutar al mismo tiempo sin que la computadora se vuelva lenta. 
                          </p>
                          <q-img
                          class="col-12 col-md-4 self-center rounded-borders"
                          src="assets/MemoriaRAM.png"
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
                          label="Tipos de Memoria RAM"
                          icon="list"
                          @click="tiposDeMemoriaRam"
                          />
        <q-dialog v-model="dialogoAbierto" persistent>
            <q-card style="max-width: 90vw; max-height: 90vh;">
                <q-card-section>
                    <div class="text-h6 text-weight-bold">Video: Procesador(CPU)</div>
                </q-card-section>
                <q-card-section class="q-pa-none">
                    <iframe 
                    width="560" height="315" 
                    src="https://www.youtube.com/embed/VzIdJubCv00?si=HYzPMzhBjFMPN0e1" 
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
    message: "La evolución de las memorias RAM ha sido fascinante, desde las DRAM de los años 70 hasta las actuales DDR5, que son significativamente más rápidas y eficientes.<br><br>\
              Aunque DDR5 apenas está comenzando a establecerse, ya se está investigando la próxima generación (DDR6). Además, las memorias de mayor especialización y eficiencia seguirán siendo clave en áreas como inteligencia artificial y realidad virtual.\
",
    ok: {
      icon:'check',
      label: '',
      class: 'q-btn--rounded',
      flat: true,
    },
    style:'width: 500px; max-width: 90vw;'
  });
};
const tiposDeMemoriaRam = () => {
  $q.dialog({
    html:true,
    title: '<div style="display: flex; justify-content: center; align-items: center; background-color: #c6feb5; border-radius: 50%; width: 50px; height: 50px; margin: 0 auto;" translate="no">\
              <i class="q-icon material-icons" style="color: #006cff; font-size: 34px;" translate="no">priority_high</i>\
            </div>',
    message: 
    "\
        <strong>1. DDR4 (Double Data Rate 4):</strong><br>\
            <ul>\
                <li>Es el estándar más común en dispositivos modernos como computadoras de escritorio, laptops y servidores.</li>\
                <li>Ofrece velocidades rápidas, bajo consumo de energía y capacidades de almacenamiento mayores que las generaciones anteriores.</li>\
                <li>Su frecuencia suele oscilar entre 2133 MHz y 3200 MHz (o más en versiones optimizadas).</li>\
            </ul>\
        <strong>2. DDR5 (Double Data Rate 5):</strong><br>\
            <ul>\
                <li>Es la evolución más reciente de la RAM DDR y está ganando popularidad rápidamente.</li>\
                <li>Proporciona mayor ancho de banda, menor latencia y una eficiencia energética aún mejor que DDR4.</li>\
                <li>Ideal para tareas de alto rendimiento como gaming, edición de video y aprendizaje automático.</li>\
            </ul>\
        <strong>3. LPDDR (Low-Power DDR):</strong><br>\
            <ul>\
                <li>Se utiliza en dispositivos móviles como smartphones, tablets y ultrabooks.</li>\
                <li>Diseñada para un consumo energético reducido, prolonga la duración de la batería en dispositivos portátiles.</li>\
                <li>Ejemplos recientes son LPDDR4 y LPDDR5.</li>\
            </ul>\
        <strong>4. GDDR (Graphics Double Data Rate):</strong><br>\
            <ul>\
                <li>Memoria especializada para tarjetas gráficas (GPUs) en aplicaciones como videojuegos, edición 3D y minería de criptomonedas.</li>\
                <li>Ejemplos actuales incluyen GDDR5, GDDR6 y GDDR6X, que ofrecen alta velocidad y capacidad para manejar grandes volúmenes de datos gráficos.</li>\
            </ul>\
        <strong>5. HBM (High Bandwidth Memory):</strong><br>\
            <ul>\
                <li>Se encuentra en sistemas de alto rendimiento, como supercomputadoras y estaciones de trabajo avanzadas.</li>\
                <li>Ofrece un ancho de banda extremadamente alto al colocar los módulos de RAM directamente cerca del procesador.</li>\
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