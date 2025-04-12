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
                                La Tarjeta Gárfica
                            </p>
                        </q-card-section>
                        <q-card-section class="row items-start items-stretch q-col-gutter-md q-row-gutter-md">
                          <p class="col-12 col-md-7 text-justify q-pr-md">
                            <strong>¿Qué es y para qué sirve La Tarjeta Gráfica?</strong><br><br>
                            Una tarjeta gráfica, también conocida como GPU (Graphics Processing Unit), 
                            es un componente esencial de una computadora que se encarga de procesar y generar las imágenes que ves en la pantalla. 
                            Desde las interfaces de usuario hasta los gráficos complejos de videojuegos o aplicaciones de diseño, 
                            la tarjeta gráfica traduce los datos del procesador en representaciones visuales comprensibles para el usuario.<br><br>
                            En resumen, la tarjeta gráfica es fundamental para cualquier tarea que requiera procesamiento visual intensivo, 
                            mejorando la calidad y fluidez de las imágenes en pantalla.  
                          </p>
                          <q-img
                          class="col-12 col-md-4 self-center rounded-borders"
                          src="assets/TarjetaGrafica.png"
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
                          label="Tipos de Tarjeta Gráfica"
                          icon="list"
                          @click="tiposDeTarjetaGrafica"
                          />
        <q-dialog v-model="dialogoAbierto" persistent>
            <q-card style="max-width: 90vw; max-height: 90vh;">
                <q-card-section>
                    <div class="text-h6 text-weight-bold">Video: Almacenamiento Principal</div>
                </q-card-section>
                <q-card-section class="q-pa-none">
                    <iframe 
                    width="560" height="315" 
                    src="https://www.youtube.com/embed/ywaGGynYSkQ?si=9-u3_L43VGIOk3Jx" 
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
    message: "\
    Las tarjetas gráficas han experimentado una notable evolución desde sus inicios en los años 80,\
    cuando apenas podían mostrar texto en pantallas monocromáticas. Con el tiempo,\
    se convirtieron en componentes capaces de procesar gráficos 3D y colores vibrantes,\
    gracias a avances como la incorporación de memoria DDR y núcleos paralelos programables.<br><br>\
    En la actualidad, las GPUs no solo se utilizan para videojuegos, sino que también desempeñan un papel\
    crucial en campos como la inteligencia artificial, el aprendizaje automático y la creación de contenido digital.\
    La integración de tecnologías como el renderizado neuronal y el DLSS 4 ha permitido mejorar significativamente\
    la calidad de imagen y el rendimiento en tiempo real.<br><br>\
    De cara al futuro, se espera que las tarjetas gráficas continúen avanzando en eficiencia energética y capacidades\
    de procesamiento, con un enfoque creciente en la integración de inteligencia artificial y aprendizaje automático.\
    Además, la tendencia hacia arquitecturas más potentes y versátiles, como la serie RTX 50 de Nvidia,\
    indica un camino hacia GPUs capaces de manejar tareas cada vez más complejas en diversos ámbitos.\
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
const tiposDeTarjetaGrafica = () => {
  $q.dialog({
    html:true,
    title: '<div style="display: flex; justify-content: center; align-items: center; background-color: #c6feb5; border-radius: 50%; width: 50px; height: 50px; margin: 0 auto;" translate="no">\
              <i class="q-icon material-icons" style="color: #006cff; font-size: 34px;" translate="no">priority_high</i>\
            </div>',
    message: 
    "Existen dos tipos principales:<br>\
            <ul>\
                <li><strong>Integradas</strong>:  Están incorporadas en el procesador o en la placa base y son adecuadas para tareas básicas como navegar por internet o utilizar aplicaciones de oficina.</li>\
                <li><strong>Dedicadas</strong>: Son componentes independientes que ofrecen un rendimiento superior, ideales para videojuegos exigentes, edición de video y diseño gráfico. Estas tarjetas cuentan con su propia memoria (VRAM) y están diseñadas específicamente para manejar gráficos pesados y complejos.</li>\
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