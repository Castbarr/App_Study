<template>
    <q-page class="q-pa-md flex flex-center">
        <div class="q-gutter-sm flex flex-center">
            <q-card class="responsive-card">
                <q-card-section>
                    <div class="text-h4 text-weight-bold text-center">¿Qué es una Computadora?</div>
                </q-card-section>

                <q-card-section>
                        <q-card-section>
                            <p class="text-h6">
                                Una computadora es un sistema compuesto por hardware y software. 
                                El hardware es la parte física y tangible, como los componentes electrónicos, 
                                mientras que el software se refiere a los programas e instrucciones que controlan el hardware. 
                                Juntos, permiten procesar datos y realizar diversas tareas según las necesidades del usuario.
                            </p>
                        </q-card-section>
                        <q-card-section class="row items-start items-stretch q-col-gutter-md q-row-gutter-md">
                          <p class="col-12 col-md-7 text-justify q-pr-md">
                            Una computadora no es solo un conjunto de hardware y software; 
                            es una herramienta que ha transformado la manera en que interactuamos con el mundo. 
                            Su uso ha trascendido lo técnico para convertirse en el núcleo de actividades cotidianas y profesionales, 
                            desde la comunicación hasta la investigación médica. En un mundo donde la digitalización avanza a pasos agigantados, 
                            las computadoras no solo procesan datos, sino que amplifican nuestra creatividad, productividad y conexión global. 
                            Sin embargo, este crecimiento también nos invita a reflexionar sobre el equilibrio entre el uso responsable 
                            de la tecnología y su impacto en nuestra vida personal y social. En esencia, las computadoras son un reflejo 
                            de nuestro ingenio, pero también un recordatorio de nuestra responsabilidad en su aplicación.
                          </p>
                          <q-img
                          class="col-12 col-md-4 self-center"
                          src="assets/DibujoComputadora.png"
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
        <q-dialog v-model="dialogoAbierto" persistent>
            <q-card style="max-width: 90vw; max-height: 90vh;">
                <q-card-section>
                    <div class="text-h6 text-weight-bold">Video: ¿Qué es una Computadora?</div>
                </q-card-section>
                <q-card-section class="q-pa-none">
                    <iframe 
                    width="560" height="315" 
                    src="https://www.youtube.com/embed/jpYeQ3ON7uc?si=zpPmTsnKmnFGDelq" 
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
    message: "En términos técnicos, y según la definición de computadora,\
              podemos considerar como tales a diversos dispositivos computables,\
              tales como los teléfonos móviles, las tablets, las consolas de videojuegos,\
              entre otros. Sin embargo, en el uso cotidiano, la palabra 'computadora'\
              suele asociarse exclusivamente a la computadora personal (PC),\
              la cual será el enfoque principal de este curso para explicar su funcionamiento.\
              Es importante destacar que los dispositivos antes mencionados operan internamente\
              de manera similar y se rigen por los mismos conceptos fundamentales.",
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