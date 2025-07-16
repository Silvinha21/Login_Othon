<template>
  <v-card
    class="mx-auto pa-6"
    max-width="600"
    elevation="3"
    color="#1e1e1e"
  >
    <v-card-title class="text-h6 text-white mb-4">Cadastro de Banco</v-card-title>

    <v-form v-model="formValid" @submit.prevent>
      <v-text-field
        v-model="numBanco"
        label="Número do Banco"
        :rules="[rules.required]"
        variant="outlined"
        color="grey-lighten-1"
        class="mb-2"
        dark
      />

      <v-text-field
        v-model="descBanco"
        label="Descrição do Banco"
        :rules="[rules.required]"
        variant="outlined"
        color="grey-lighten-1"
        class="mb-4"
        dark
      />

      <v-switch
      label="Banco Ativo?"
      color="primary"
      value="ativo"
      >

      </v-switch>

      <v-btn
        block
        color="primary"
        size="large"
        class="mb-4 text-white"
        @click="salvar"
      >
        Salvar
      </v-btn>
    </v-form>

  </v-card>
</template>

<script setup>
import { ref } from 'vue'

const numBanco = ref('')
const descBanco = ref('')
const formValid = ref(false)

const rules = {
  required: value => !!value || 'Campo obrigatório',
}

const salvar = () => {
  if (!formValid.value) return
  // Lógica futura de login
}

</script>

<style scoped>
.v-card {
  background-color: #1e1e1e !important;
}
</style>