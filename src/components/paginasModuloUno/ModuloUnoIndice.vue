<template>
    <q-page class="q-pa-sm flex flex-center">
        <div class="q-gutter-sm flex flex-center">
            <q-card class="responsive-card">
                <q-card-section class="col flex flex-column items-center text-center">
                    <div>
                        <h4 class="text-weight-bold">Modulo 1</h4>
                        <h5 style="margin-top: 0; margin-bottom: 0;">Introducción a los Fundamentos de la Computación</h5>
                    </div>
                </q-card-section>

                <q-card-section>
                    <div class="row flex-wrap justify-evenly">
                        <div class="col-12 col-md-6 flex column items-center q-mt-none">
                            <h5 class="text-center">Objetivos</h5>
                            <ul>
                                <li>Introducción al concepto de Computación y Computadora.</li>
                                <li>Exploración de las partes físicas de una computadora: el hardware y sus funciones.</li>
                                <li>Comprensión del software: definición, funcionamiento y su importancia en la informática.</li>
                            </ul>
                        </div>
                        <div class="col-12 col-md-6 flex flex-center">
                            <img src="assets/computadora.png" alt="computadoras" class="responsive-img" style="border-radius: 15px;">
                        </div>
                    </div>
                </q-card-section>
            </q-card>
        </div>
    </q-page>
</template>

<script setup>
</script>

<style scoped>
/* Ajusta la tarjeta para que sea responsiva */
.responsive-card {
    max-width: 90%;
    max-height: 90%;
    width: 100%;
    height: auto;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}

/* Asegura que las imágenes sean responsivas */
.responsive-img {
    max-width: 60%;
    height: auto;
}

/* Ajusta el espaciado en pantallas pequeñas */
@media (max-width: 600px) {
    .q-card-section {
        padding: 10px;
    }
}
</style>