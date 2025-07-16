<template>
  <v-card
    class="mx-auto pa-6"
    max-width="600"
    elevation="3"
    color="#1e1e1e"
  >
    <v-card-title class="text-h6 text-white mb-4">Login</v-card-title>

    <v-form v-model="formValido" @submit.prevent>
      <v-text-field
        v-model="email"
        label="E-mail"
        placeholder="exemplo@gmail.com"
        type="email"
        :rules="[rules.required]"
        variant="outlined"
        color="grey-lighten-1"
        class="mb-2"
        dark
      />

      <v-text-field
        v-model="senha"
        label="Senha"
        type="password"
        :rules="[rules.required]"
        variant="outlined"
        color="grey-lighten-1"
        class="mb-4"
        dark
      />

      <v-btn
        block
        color="primary"
        size="large"
        class="mb-4 text-white"
        @click="login"
      >
        ENTRAR
      </v-btn>
    </v-form>

    <v-btn variant="text" block class="text-white text-uppercase" @click="criarConta">
      Criar Conta
    </v-btn>
  </v-card>
</template>

<script setup>
import { ref } from 'vue'

const email = ref('')
const senha = ref('')
const formValido = ref(false)

const rules = {
  required: value => !!value || 'Campo obrigatório',
}

const login = () => {
  if (!formValid.value) return
  // Botar oq acontece se apertar no login
}

const criarConta = () => {
  // configurar o roteamento para ir para a pagína de cadastro de conta
}
</script>

<style scoped>
.v-card {
  background-color: #1e1e1e !important;
}
</style>