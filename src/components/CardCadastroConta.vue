<template>
  <v-card
    class="mx-auto pa-6"
    max-width="700"
    elevation="10"
    color="#1e1e1e"
  >
    <v-card-title class="text-h6 text-white mb-4">
      Cadastro de Conta Bancária
    </v-card-title>

    <v-form v-model="formValid" @submit.prevent>
      <v-row dense>
        <v-col cols="12" md="4">
          <v-select
            v-model="banco"
            :items="bancosDisponiveis"
            label="Banco"
            :rules="[rules.required]"
            variant="outlined"
            color="grey-lighten-1"
            dark
          />
        </v-col>

        <v-col cols="12" md="4">
          <v-text-field
            v-model="agencia"
            label="Agência"
            :rules="[rules.required]"
            variant="outlined"
            color="grey-lighten-1"
            dark
          />
        </v-col>

        <v-col cols="12" md="4">
          <v-text-field
            v-model="digitoAgencia"
            label="Dígito da Agência"
            :rules="[rules.required]"
            variant="outlined"
            color="grey-lighten-1"
            dark
          />
        </v-col>

        <v-col cols="12" md="6">
          <v-text-field
            v-model="numeroConta"
            label="Número da Conta"
            :rules="[rules.required]"
            variant="outlined"
            color="grey-lighten-1"
            dark
          />
        </v-col>

        <v-col cols="12" md="6">
          <v-text-field
            v-model="digitoConta"
            label="Dígito da Conta"
            :rules="[rules.required]"
            variant="outlined"
            color="grey-lighten-1"
            dark
          />
        </v-col>

        <v-col cols="12">
          <v-text-field
            v-model="saldoInicial"
            label="Saldo Inicial"
            type="number"
            :rules="[rules.required]"
            variant="outlined"
            color="grey-lighten-1"
            dark
          />
        </v-col>

        <v-col cols="12">
          <v-text-field
            v-model="dataCriacao"
            label="Data de Criação"
            placeholder="mm/dd/yyyy"
            :rules="[rules.required, rules.date]"
            variant="outlined"
            color="grey-lighten-1"
            dark
            append-inner-icon="mdi-calendar"
          />
        </v-col>

        <v-col cols="12">
          <v-switch
            v-model="contaAtiva"
            label="Conta Ativa"
            color="primary"
            
          />
        </v-col>

        <v-col cols="12">
          <v-btn
            block
            color="primary"
            size="large"
            class="text-white"
            @click="salvarConta"
          >
            SALVAR CONTA
          </v-btn>
        </v-col>
      </v-row>
    </v-form>
  </v-card>
</template>

<script setup>
import { ref } from 'vue'

const formValid = ref(false)

const banco = ref('')
const agencia = ref('')
const digitoAgencia = ref('')
const numeroConta = ref('')
const digitoConta = ref('')
const saldoInicial = ref(null)
const dataCriacao = ref('')
const contaAtiva = ref(true)

const bancosDisponiveis = [
  'Banco do Brasil',
  'Santander',
  'Caixa Econômica Federal',
  'Itaú',
]

const rules = {
  required: v => !!v || 'Campo obrigatório',
  date: v => /^\d{2}\/\d{2}\/\d{4}$/.test(v) || 'Formato esperado: mm/dd/yyyy',
}

const salvarConta = () => {
  if (!formValid.value) return
  // lógica futura para envio dos dados
}
</script>

<style scoped>
.v-card {
  background-color: #1e1e1e !important;
}
</style>
