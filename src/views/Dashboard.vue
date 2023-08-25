<template>
    <v-main>
        <v-container>
            <h1 class="mb-4">Dashboard</h1>
            <app-bar></app-bar>
            <funcionarios-table-vue></funcionarios-table-vue>
            <cards-panel></cards-panel>
        </v-container>
    </v-main>
</template>

<script setup>

import FuncionariosTableVue from '@/components/tables/FuncionariosTable.vue';
import CardsPanel from '@/components/cards/CardsPanel.vue';
import AppBar from '@/components/bar/AppBar.vue';

</script>

<script>
export default {
}
</script>

<style></style>