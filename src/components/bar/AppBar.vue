<template>
    <v-navigation-drawer v-model="isDrawerOpen">
        <v-list>
            <v-list-subheader>
                Menu
            </v-list-subheader>
            <v-list-item prepend-icon="mdi-home">
                Home
            </v-list-item>
            <v-list-item prepend-icon="mdi-account">
                Usuários
            </v-list-item>
            <v-list-group value="Clientes">
                <template #activator="{ props }">
                    <v-list-item v-bind="props" prepend-icon="mdi-account-circle">
                        Clientes
                    </v-list-item>
                </template>
                <v-list-item prepend-icon="mdi-currency-usd">
                    Vendas
                </v-list-item>
                <v-list-item prepend-icon="mdi-chart-line">
                    Relatórios
                </v-list-item>

            </v-list-group>
        </v-list>
    </v-navigation-drawer>
    <v-app-bar flat class="border-b">
        <v-app-bar-nav-icon @click="isDrawerOpen = !isDrawerOpen"></v-app-bar-nav-icon>
        <v-app-bar-title>
            Meu App
        </v-app-bar-title>

        <template #append>
            <v-btn @click="toggleTheme">Toogle theme</v-btn>

            <v-btn icon class="mr-2">
                <v-badge dot color="info">
                    <v-icon icon="mdi-bell-outline"></v-icon>
                </v-badge>
            </v-btn>

            <v-menu>
                <template #activator="{ props }">
                    <v-avatar v-bind="props">
                        <v-img src="https://www.ecp.org.br/wp-content/uploads/2017/12/default-avatar-300x300.png"
                            cover></v-img>
                    </v-avatar>
                </template>

                <v-card min-width="200">
                    <v-list :lines="false" density="compact" nav>
                        <v-list-item prepend-icon="mdi-account-outline">
                            <v-list-item-title>
                                Meu perfil
                            </v-list-item-title>
                        </v-list-item>
                        <v-list-item prepend-icon="mdi-heart-outline">
                            <v-list-item-title>
                                Meus favoritos
                            </v-list-item-title>
                        </v-list-item>
                    </v-list>
                </v-card>
            </v-menu>

        </template>

    </v-app-bar>
</template>

<script setup>
import { ref } from 'vue';
import { useTheme } from 'vuetify'

const theme = useTheme()

function toggleTheme() {
    theme.global.name.value = theme.global.current.value.dark ? 'light' : 'dark'
}
const isDrawerOpen = ref(false)
</script>

<script>
export default {

}
</script>

<style></style>