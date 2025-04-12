<template>
    <q-page class="flex flex-center">
        <div>
            <component :is="pages[currentPage]" />
        </div>
        <q-footer class="footer">
            <q-btn flat rounded color="primary" @click="navigate('previous')" icon="arrow_back"/>
            <q-btn flat rounded color="primary" @click="navigate('next')" icon="arrow_forward"/>
        </q-footer>
    </q-page>
</template>

<script setup>
import { ref } from 'vue';
import ModuloUnoIndice from './paginasModuloUno/ModuloUnoIndice.vue';
import ModuloUnoPaginaUno from './paginasModuloUno/ModuloUnoPaginaUno.vue';
import ModuloUnoPaginaDos from './paginasModuloUno/ModuloUnoPaginaDos.vue'; 
import ModuloUnoPaginaTres from './paginasModuloUno/ModuloUnoPaginaTres.vue';
import ModuloUnoPaginaCuatro from './paginasModuloUno/ModuloUnoPaginaCuatro.vue';
import ModuloUnoPaginaCinco from './paginasModuloUno/ModuloUnoPaginaCinco.vue';
import ModuloUnoPaginaSeis from './paginasModuloUno/ModuloUnoPaginaSeis.vue';
import ModuloUnoPaginaDiez from './paginasModuloUno/ModuloUnoPaginaDiez.vue';
import ModuloUnoPaginaSiete from './paginasModuloUno/ModuloUnoPaginaSiete.vue';

const currentPage = ref(1);

const pages = {
    1: ModuloUnoIndice,
    2: ModuloUnoPaginaUno,
    3: ModuloUnoPaginaDos,
    4: ModuloUnoPaginaTres,
    5: ModuloUnoPaginaCuatro,
    6: ModuloUnoPaginaCinco,
    7: ModuloUnoPaginaSeis,
    8: ModuloUnoPaginaSiete,
    9: ModuloUnoPaginaDiez,
};

function navigate(direction) {
    if (direction === "previous" && currentPage.value > 1) {
        currentPage.value--;
    } else if (direction === "next" && currentPage.value < Object.keys(pages).length) {
        currentPage.value++;
    }
}

</script>

<style scoped>


.footer {
    display: flex;
    justify-content: space-between;
    padding: 10px;
    background-color: #f1f1f1;
}
</style>
