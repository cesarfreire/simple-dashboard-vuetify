<template>
    <v-card flat class="border mb-4">
        <div class="d-flex justify-space-between">
            <v-card-title>Últimos usuários</v-card-title>

            <v-card-title>
                <v-dialog width="600px" v-model="isDialogOpen">
                    <template v-slot:activator="{ props }">
                        <v-btn v-bind="props" variant="tonal" size="small">
                            Adicionar usuário
                        </v-btn>
                    </template>

                    <v-card>
                        <v-card-title>Adicionar usuário</v-card-title>
                        <v-card-text>
                            <v-row>
                                <v-col>
                                    <v-text-field label="Nome" variant="outlined"></v-text-field>
                                </v-col>
                                <v-col>
                                    <v-text-field label="Email" variant="outlined" :rules="emailRules"></v-text-field>
                                </v-col>
                            </v-row>
                            <v-select label="Cargo" variant="outlined" :items="['Admin', 'Gerente', 'Convidado']">

                            </v-select>
                        </v-card-text>

                        <v-card-actions>
                            <v-spacer></v-spacer>
                            <v-btn variant="tonal" color="success">
                                Salvar
                            </v-btn>
                            <v-btn variant="text" @click="isDialogOpen = false">
                                Fechar
                            </v-btn>
                        </v-card-actions>
                    </v-card>

                </v-dialog>

            </v-card-title>
        </div>

        <v-table>
            <thead>
                <tr>
                    <th>Nome</th>
                    <th>E-mail</th>
                    <th>Cargo</th>
                    <th>Ações</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>Fulano</td>
                    <td>fulano@gmail.com</td>
                    <td>
                        <v-chip color="primary" variant="outlined" size="small">Admin</v-chip>
                    </td>
                    <td>
                        <v-btn variant="tonal" color="primary" prepend-icon="mdi-pencil">
                            Editar
                        </v-btn>
                    </td>
                </tr>
                <tr>
                    <td>Fulano</td>
                    <td>fulano@gmail.com</td>
                    <td>
                        <v-chip color="success" variant="outlined" size="small">Gerente</v-chip>
                    </td>
                    <td>
                        <v-btn variant="tonal" color="primary" prepend-icon="mdi-pencil">
                            Editar
                        </v-btn>
                    </td>
                </tr>
                <tr>
                    <td>Fulano</td>
                    <td>fulano@gmail.com</td>
                    <td>
                        <v-chip variant="outlined" size="small">Analista</v-chip>
                    </td>
                    <td>
                        <v-btn variant="tonal" color="primary" prepend-icon="mdi-pencil">
                            Editar
                        </v-btn>
                    </td>
                </tr>
            </tbody>
        </v-table>
    </v-card>
</template>

<script setup>
import { ref } from 'vue';
const isDialogOpen = ref(false)
const emailRules = [
    value => {
        if (value) return true

        return 'O e-mail é obrigatório.'
    },

    value => {
        if (value.includes('@')) return true

        return 'O e-mail não é válido.'
    }
]
</script>
<script>
export default {

}
</script>

<style></style>