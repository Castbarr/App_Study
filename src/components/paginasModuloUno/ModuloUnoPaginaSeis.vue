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
                                La Unidad de Almacenamiento Principal
                            </p>
                        </q-card-section>
                        <q-card-section class="row items-start items-stretch q-col-gutter-md q-row-gutter-md">
                          <p class="col-12 col-md-7 text-justify q-pr-md">
                            <strong>¿Qué es y para qué sirve La Unidad de Almacenamiento Principal?</strong><br><br>
                            La Unidad de almacenamiento principal de una computadora —ya sea un disco duro (HDD), una unidad de estado sólido (SSD) o algo similar— es básicamente el lugar donde se guarda todo lo importante en tu computadora. Piensa en él como una especie de “closet digital” donde metes tus archivos, programas, fotos, videos, juegos y hasta el sistema operativo (como Windows, Linux o macOS).<br><br>
                            Cuando prendes tu computadora, lo primero que hace es ir al disco principal a buscar el sistema para poder arrancar y funcionar. Sin ese disco, la computadora no sabría ni por dónde empezar.<br><br>
                            En resumen, la unidad de almacenamiento principal es el corazón de tu computadora, y sirve para:<br>
                            &nbsp;&nbsp;💾Guardar todos tus archivos, programas, juegos, etc.<br>
                            &nbsp;&nbsp;💾Guardar y Arrancar el sistema operativo.<br>
                            &nbsp;&nbsp; 🖴 Almacenar datos de forma permanente (a diferencia de la RAM, que es temporal).  
                          </p>
                          <q-img
                          class="col-12 col-md-4 self-center rounded-borders"
                          src="../../assets/CollageDiscos.png"
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
                          label="Tipos de Unidad de Almacenamiento"
                          icon="list"
                          @click="tiposDeUnidadAlmacenamiento"
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
    🔄 <strong>Evolución</strong><br>\
        <ul>\
            <li>HDD (Disco Duro)\
                <ul>\
                    <li>Surgió en los años 50.</li>\
                    <li>Basado en discos magnéticos y partes mecánicas.</li>\
                    <li>Gran capacidad, bajo costo, pero lento y frágil.</li>\
                </ul>\
            </li>\
            <li>SSD (Unidad de Estado Sólido)<br>\
                <ul>\
                    <li>Aparece masivamente en los 2000s.</li>\
                    <li>Usa memoria flash, sin partes móviles.</li>\
                    <li>Mucho más rápido, silencioso y resistente.</li>\
                </ul>\
            </li>\
        </ul>\
        🔮 <strong>Futuro</strong><br>\
        <ul>\
            <li>Mejoras en memoria flash: 3D NAND, QLC → mayor capacidad y menor precio.</li>\
            <li>NVMe sobre PCIe: velocidades ultra rápidas.</li>\
            <li>Memoria persistente (PMEM): fusión de RAM + almacenamiento.</li>\
            <li>Almacenamiento híbrido y en la nube: más flexible y escalable.</li>\
            <li>Exploración futura: almacenamiento molecular, óptico y cuántico.</li>\
        </ul>\
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
const tiposDeUnidadAlmacenamiento = () => {
  $q.dialog({
    html:true,
    title: '<div style="display: flex; justify-content: center; align-items: center; background-color: #c6feb5; border-radius: 50%; width: 50px; height: 50px; margin: 0 auto;" translate="no">\
              <i class="q-icon material-icons" style="color: #006cff; font-size: 34px;" translate="no">priority_high</i>\
            </div>',
    message: 
    "Hay dos tipos principales:<br>\
            <ul>\
                <li><strong>HDD (disco duro tradicional)</strong>: Es como un pequeño tocadiscos que guarda los datos en platos que giran. Tiene partes mecánicas, por eso es un poco más lento, pero suelen tener mucha capacidad y ser más baratos.</li>\
                <li><strong>SSD (unidad de estado sólido)</strong>: No tiene partes móviles. Es mucho más rápido que el HDD y hace que la computadora prenda y cargue programas en segundos. El único detalle es que suelen ser más caros por cada gigabyte de espacio.</li>\
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