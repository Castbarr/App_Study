<template>
    <q-page class="q-pa-md flex flex-center">
        <div class="q-gutter-sm flex flex-center">
            <q-card class="responsive-card">
                <q-card-section>
                    <div class="text-h5 text-weight-bold text-center">Hardware</div>
                </q-card-section>

                <q-card-section>
                        <q-card-section>
                            <p class="text-h6">
                                La parte física de la Computadora.
                            </p>
                        </q-card-section>
                        <q-card-section class="row items-start items-stretch q-col-gutter-md q-row-gutter-md">
                          <p class="col-12 col-md-7 text-justify q-pr-md">
                            El hardware de una computadora es, esencialmente, su cuerpo físico, 
                            los componentes tangibles que interactúan entre sí para realizar procesos computacionales. 
                            Es como la maquinaria detrás de una obra de arte tecnológica, cada pieza desempeña un papel crucial.<br>
                            <br>
                            El hardware refleja la evolución tecnológica y su capacidad de adaptación. 
                            Cada componente es resultado de décadas de investigación e innovación. 
                            Por ejemplo, los avances en materiales y diseño han permitido crear dispositivos más pequeños y eficientes, 
                            como laptops ultralivianos o teléfonos inteligentes.<br><br> Pero no solo es tecnología: 
                            el hardware también nos conecta con un mundo digital que influye en nuestra vida diaria. 
                            Sin un hardware funcional, el software, que es el "alma" de la computadora, 
                            no tendría un medio para manifestarse. Es una relación simbiótica donde uno no existe sin el otro.
                          </p>
                          <q-img
                          class="col-12 col-md-4 self-center rounded-borders"
                          src="assets/hardware.png"
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
                          label="Componentes Internos"
                          icon="list"
                          @click="componentesInternos"
                          />
                          <q-btn
                          class="blink q-ma-md q-pa-sm self-center"
                          color="secondary"
                          label="Periféricos"
                          icon="list"
                          @click="componentesPerifericos"
                          />
        <q-dialog v-model="dialogoAbierto" persistent>
            <q-card style="max-width: 90vw; max-height: 90vh;">
                <q-card-section>
                    <div class="text-h6 text-weight-bold">Video: Hardware</div>
                </q-card-section>
                <q-card-section class="q-pa-none">
                    <iframe 
                    width="560" height="315" 
                    src="https://www.youtube.com/embed/BfEn8SrhAag?si=o8-MfYxSuCtYFw66" 
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
    message: "Un apunte importante sobre el <em>hardware</em> es que su desempeño y capacidad están directamente relacionados con el software que ejecuta. Es decir, un mismo <em>hardware</em> puede tener un rendimiento muy diferente según la optimización del software, los controladores utilizados y el sistema operativo en el que se ejecuta. Además, el <em>hardware</em> evoluciona constantemente, por lo que su obsolescencia es un factor clave a considerar en el desarrollo y mantenimiento de sistemas informáticos.",
    ok: {
      icon:'check',
      label: '',
      class: 'q-btn--rounded',
      flat: true,
    },
    style:'width: 500px; max-width: 90vw;'
  });
};
const componentesInternos = () => {
  $q.dialog({
    html:true,
    title: '<div style="display: flex; justify-content: center; align-items: center; background-color: #c6feb5; border-radius: 50%; width: 50px; height: 50px; margin: 0 auto;" translate="no">\
              <i class="q-icon material-icons" style="color: #006cff; font-size: 34px;" translate="no">priority_high</i>\
            </div>',
    message: 
    "<ul>\
        <li>Procesador(CPU)</li>\
        <li>Placa base(Motherboard)</li>\
        <li>Memoria RAM</li>\
        <li>Disco Duro o SSD</li>\
        <li>Tarjeta gráfica(GPU)</li>\
        <li>Fuente de alimentación</li>\
        <li>Unidad de refrigeración(ventiladores o sistemas líquidos)</li>\
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
const componentesPerifericos = () => {
  $q.dialog({
    html:true,
    title: '<div style="display: flex; justify-content: center; align-items: center; background-color: #c6feb5; border-radius: 50%; width: 50px; height: 50px; margin: 0 auto;" translate="no">\
              <i class="q-icon material-icons" style="color: #006cff; font-size: 34px;" translate="no">priority_high</i>\
            </div>',
    message: 
    "<ul>\
        <li>Monitor</li>\
        <li>Teclado</li>\
        <li>Ratón(mouse)</li>\
        <li>Impresora</li>\
        <li>Escáner</li>\
        <li>Cámara web</li>\
        <li>Bocinas</li>\
        <li>Audífonos</li>\
        <li>Micrófono</li>\
        <li>Dispositivos de almacenamiento externo(USB, discos externos)</li>\
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