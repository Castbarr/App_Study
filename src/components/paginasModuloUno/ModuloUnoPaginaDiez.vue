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
                                Placa Base(Motherboard)
                            </p>
                        </q-card-section>
                        <q-card-section class="row items-start items-stretch q-col-gutter-md q-row-gutter-md">
                          <p class="col-12 col-md-7 text-justify q-pr-md">
                            La placa base (o motherboard) es como el "esqueleto" de una computadora. Es una gran tarjeta de circuito donde se conectan y comunican todas las partes esenciales del equipo. Imagina que es como una ciudad con calles y avenidas por donde viajan los datos de un lado a otro.<br><br>
                            En la placa base se instalan el procesador (CPU), que es el cerebro de la computadora; la memoria RAM, que es donde se guardan los datos temporales mientras trabajamos; y las tarjetas de expansión (como la de video o sonido), que agregan funciones extra. También tiene conectores para los discos duros, puertos USB, y la fuente de alimentación que le da energía a todo el sistema.<br><br>
                            En resumen, la placa base es el centro de conexión de todos los componentes de la computadora. Sin ella, las piezas estarían desconectadas y el equipo simplemente no funcionaría. Es la base sobre la que todo lo demás se construye.
                          </p>
                          <q-img
                          class="col-12 col-md-4 self-center rounded-borders"
                          src="assets/TarjetaMadre.png"
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
                          label="Partes de la Placa Base"
                          icon="list"
                          @click="partesDelaPlacaBase"
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
    message: "No todas las placas base son compatibles con todos los procesadores. Cada placa tiene un socket específico y un chipset que determinan qué CPU puede usar. Antes de cambiar o actualizar un procesador, es fundamental verificar la compatibilidad con la placa base.",
    ok: {
      icon:'check',
      label: '',
      class: 'q-btn--rounded',
      flat: true,
    },
  });
};
const partesDelaPlacaBase = () => {
  $q.dialog({
    html:true,
    title: '<div style="display: flex; justify-content: center; align-items: center; background-color: #c6feb5; border-radius: 50%; width: 50px; height: 50px; margin: 0 auto;" translate="no">\
              <i class="q-icon material-icons" style="color: #006cff; font-size: 34px;" translate="no">priority_high</i>\
            </div>',
    message: 
    "<ul>\
        <li><strong>Zócalo del procesador (CPU Socket):</strong><br>Es el lugar donde se instala el procesador. Su tipo y tamaño dependen del modelo y la marca de la CPU (Intel o AMD).</li>\
        <li><strong>Ranuras de memoria RAM (DIMM Slots):</strong><br>Son los espacios donde se colocan los módulos de memoria RAM. Pueden ser DDR3, DDR4 o DDR5, según la placa.</li>\
        <li><strong>Chipset:</strong><br>Es el conjunto de chips que gestiona la comunicación entre el procesador, la memoria, y otros componentes. Se divide en:<br>\
            <ul>\
                <li><strong>Northbridge</strong> (en modelos antiguos) → Maneja la comunicación con la RAM y la tarjeta gráfica.</li>\
                <li><strong>Southbridge</strong> (o PCH en modelos modernos) → Administra los dispositivos de almacenamiento y puertos de entrada/salida.</li>\
            </ul>\
            </li>\
        <li><strong>Ranuras de expansión (PCIe, PCI, AGP):</strong><br>Se usan para conectar tarjetas de video, sonido, red, capturadoras, etc.<br>PCIe (PCI Express) es el más moderno y rápido.</li>\
        <li><strong>Conectores SATA / M.2:</strong><br>SATA → Para conectar discos duros (HDD), SSD y unidades de DVD.<br>M.2 → Para unidades SSD ultrarrápidas, directamente integradas en la placa.</li>\
        <li><strong>Conectores de alimentación (ATX 24 pines y CPU 4/8 pines):</strong><br>Aquí se conecta la fuente de poder para suministrar electricidad a la placa y a los componentes.</li>\
        <li><strong>BIOS / UEFI:</strong><br>Un chip que almacena el software básico para arrancar y configurar el sistema.</li>\
        <li><strong>Batería CMOS:</strong><br>Guarda la configuración del BIOS, como la fecha y la hora.</li>\
        <li><strong>Puertos de entrada/salida (I/O Panel):</strong><br>Son los conectores traseros que permiten conectar USB, HDMI, audio, red (Ethernet), etc.</li>\
        <li><strong>Disipadores y VRM (Módulo Regulador de Voltaje):</strong><br>Los disipadores ayudan a enfriar la placa y los VRM regulan la energía que llega al procesador y la RAM.</li>\
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