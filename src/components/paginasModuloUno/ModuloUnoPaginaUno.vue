<template>
    <q-page class="q-pa-md flex flex-center">
        <div class="q-gutter-sm flex flex-center">
            <q-card class="responsive-card">
                <q-card-section>
                    <div class="text-h5 text-weight-bold text-center">¿Qué es la Computación?</div>
                </q-card-section>

                <q-card-section>
                        <q-card-section>
                            <p class="text-h6">
                                La computación es el estudio y la aplicación de métodos y tecnologías para procesar,
                                almacenar y transmitir información mediante sistemas electrónicos, como las computadoras.
                                Se basa en conceptos matemáticos, lógicos y tecnológicos para resolver problemas y desarrollar soluciones eficientes.
                                Es el corazón de casi todo lo que usamos hoy en día: desde software y redes hasta inteligencia artificial y datos masivos.
                            </p>
                        </q-card-section>
                        <q-card-section class="row items-start items-stretch q-col-gutter-md q-row-gutter-md">
                            <p class="col-12 col-md-7 text-justify q-pr-md">
                                La computación ha transformado profundamente la forma en que interactuamos con el mundo, 
                                convirtiéndose en una herramienta esencial para el desarrollo de la sociedad moderna. 
                                Este campo no solo implica el estudio de cómo procesar, almacenar y transmitir información, 
                                sino que también promueve la innovación mediante la creación de soluciones tecnológicas que mejoran nuestra calidad de vida.
                                Gracias a los fundamentos matemáticos, lógicos y tecnológicos que lo sustentan, 
                                la computación permite resolver problemas complejos de manera eficiente, 
                                desde optimizar sistemas de transporte hasta analizar datos masivos para tomar decisiones informadas. 
                                Su impacto abarca áreas como el desarrollo de software, la configuración de redes, 
                                el avance de la inteligencia artificial y la gestión de grandes volúmenes de datos.
                                En resumen, la computación no solo está presente en los dispositivos que usamos diariamente, 
                                sino que también es el motor que impulsa el progreso en sectores clave como la medicina, 
                                la educación y la comunicación. Su capacidad de adaptarse y evolucionar la convierte en un pilar indispensable para enfrentar los retos del futuro.
                            </p>
                            <q-img
                            class="col-5 self-center"
                            src="assets/computacion.png"
                            style="max-height: 300px; max-width: 300px; object-fit: contain;"
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
                    <div class="text-h6 text-weight-bold">Video: ¿Qué es la Computación?</div>
                </q-card-section>
                <q-card-section class="q-pa-none">
                    <iframe 
                    width="560" height="315" 
                    src="https://www.youtube.com/embed/-jFjr0pHKXQ?si=CJGVs6UuVc-rLHnM" 
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
import { ref } from 'vue';

// Estado para controlar si el diálogo está abierto
const dialogoAbierto = ref(false);

// Función para abrir el diálogo
const mostrarVideo = () => {
    dialogoAbierto.value = true;
};
</script>

<style scoped>
/* Ajusta el estilo del iframe para que sea responsivo */
iframe {
    border-radius: 8px;
}
</style>