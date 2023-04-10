<script setup>
import { ref } from 'vue'

const nome = ref('')
const email = ref('')
const senha = ref('')
const confirmaSenha = ref('')
const dataNascimento = ref('')
const endereco = ref('')
const cidade = ref('')
const estado = ref('')
const estadoDesc = ref('')
const hobbies = ref('')
const linguagensProg = ref([])
const biografia = ref('')
const mostrarDiv = ref(false)
const msgErro = ref('')

function validarSenha() {
  atualizaEstado();
  if (senha.value === confirmaSenha.value) {
    msgErro.value = ''
    return true
  } else {
    msgErro.value = 'Erro: Senha e Confirmação de Senha não conferem!'
    return false
  }
}

function atualizaEstado() {
switch (estado.value) {
  case 'AC':
    estadoDesc.value = 'Acre'
    break
  case 'AL':
    estadoDesc.value = 'Alagoas'
    break
  case 'AP':
    estadoDesc.value = 'Amapá'
    break
  case 'AM':
    estadoDesc.value = 'Amazonas'
    break
  case 'BA':
    estadoDesc.value = 'Bahia'
    break
  case 'CE':
    estadoDesc.value = 'Ceará'
    break
  case 'DF':
    estadoDesc.value = 'Distrito Federal'
    break
  case 'ES':
    estadoDesc.value = 'Espírito Santo'
    break
  case 'GO':
    estadoDesc.value = 'Goiás'
    break
  case 'MA':
    estadoDesc.value = 'Maranhão'
    break
  case 'MT':
    estadoDesc.value = 'Mato Grosso'
    break
  case 'MS':
    estadoDesc.value = 'Mato Grosso do Sul'
    break
  case 'MG':
    estadoDesc.value = 'Minas Gerais'
    break
  case 'PA':
    estadoDesc.value = 'Pará'
    break
  case 'PB':
    estadoDesc.value = 'Paraíba'
    break
  case 'PR':
    estadoDesc.value = 'Paraná'
    break
  case 'PE':
    estadoDesc.value = 'Pernambuco'
    break
  case 'PI':
    estadoDesc.value = 'Piauí'
    break
  case 'RJ':
    estadoDesc.value = 'Rio de Janeiro'
    break
  case 'RN':
    estadoDesc.value = 'Rio Grande do Norte'
    break
  case 'RS':
    estadoDesc.value = 'Rio Grande do Sul'
    break
  case 'RO':
    estadoDesc.value = 'Rondônia'
    break
  case 'RR':
    estadoDesc.value = 'Roraima'
    break
  case 'SC':
    estadoDesc.value = 'Santa Catarina'
    break
  case 'SP':
    estadoDesc.value = 'São Paulo'
    break
  case 'SE':
    estadoDesc.value = 'Sergipe'
    break
  case 'TO':
    estadoDesc.value = 'Tocantins'
    break
}
}
</script>

<template>
  <form @submit.prevent="mostrarDiv = validarSenha()">
    <div class="info">
      <h1>Formulário</h1>
      <label>Nome:</label>
      <input
        type="text"
        v-model="nome"
        v-on:keypress="mostrarDiv = false"
        placeholder="Digite seu nome"
        required
      />
      <p>
        <label>Email:</label>
        <input
          type="email"
          v-model="email"
          v-on:keypress="mostrarDiv = false"
          placeholder="ex.:xxxx@xx.xxx"
          required
        />
      </p>
      <p>
        <label>Senha:</label>
        <input
          type="password"
          v-model="senha"
          v-on:keypress="mostrarDiv = false"
          placeholder="Digite sua senha"
          minlength="5"
          required
        />
      </p>
      <p>
        <label>Confirme sua senha:</label>
        <input
          type="password"
          v-model="confirmaSenha"
          v-on:keypress="mostrarDiv = false"
          placeholder="Confirme sua senha"
          minlength="5"
          required
        />
      </p>
      <p>
        <label>Data de nascimento:</label>
        <input type="date" v-model="dataNascimento" required />
      </p>
      <p>
        <label>Endereço:</label>
        <input
          type="text"
          v-model="endereco"
          v-on:keypress="mostrarDiv = false"
          placeholder="Digite seu endereço"
          required
        />
      </p>
      <p>
        <label>Cidade:</label>
        <input
          type="string"
          v-model="cidade"
          v-on:keypress="mostrarDiv = false"
          placeholder="Digite sua cidade"
          required
        />
      </p>
      <p>
        <label for="estado">Estado:</label>
        <select v-model="estado" required>
          <option value="AC">AC</option>
          <option value="AL">AL</option>
          <option value="AP">AP</option>
          <option value="AM">AM</option>
          <option value="BA">BA</option>
          <option value="CE">CE</option>
          <option value="DF">DF</option>
          <option value="ES">ES</option>
          <option value="GO">GO</option>
          <option value="MA">MA</option>
          <option value="MT">MT</option>
          <option value="MS">MS</option>
          <option value="MG">MG</option>
          <option value="PA">PA</option>
          <option value="PB">PB</option>
          <option value="PR">PR</option>
          <option value="PE">PE</option>
          <option value="PI">PI</option>
          <option value="RJ">RJ</option>
          <option value="RN">RN</option>
          <option value="RS">RS</option>
          <option value="RO">RO</option>
          <option value="RR">RR</option>
          <option value="SC">SC</option>
          <option value="SP">SP</option>
          <option value="SE">SE</option>
          <option value="TO">TO</option>
        </select>
      </p>
      <p>
        <label>Hobbies:</label>
      </p>
      <textarea
        v-model="hobbies"
        cols="40"
        rows="5"
        v-on:keypress="mostrarDiv = false"
        placeholder="Digite seus hobbies"
        required
      ></textarea>
      <p>
        <label>Linguagens de programação:</label>
      </p>
      <input type="checkbox" v-model="linguagensProg" value="JavaScript" /> JavaScript
      <input type="checkbox" v-model="linguagensProg" value="PHP" /> PHP
      <input type="checkbox" v-model="linguagensProg" value="C++" /> C++
      <input type="checkbox" v-model="linguagensProg" value="SQL" /> SQL
      <input type="checkbox" v-model="linguagensProg" value="Python" /> Python
      <p>
        <label>Biografia:</label>
      </p>
      <p>
        <textarea
          v-model="biografia"
          cols="40"
          rows="5"
          v-on:keypress="mostrarDiv = false"
          placeholder="Digite sua biografia"
          required
        ></textarea>
      </p>
      <button type="submit">Enviar</button>
    </div>
    <p class="erro">{{ msgErro }}</p>
  </form>
  <div v-if="mostrarDiv" class="dados">
    <p class="ok">Dados enviados com sucesso!!</p>
    <p>Nome: {{ nome }}</p>
    <p>Email: {{ email }}</p>
    <p>Senha: {{ senha }}</p>
    <p>Senha confirmada: {{ confirmaSenha }}</p>
    <p>Data de nascimento: {{ dataNascimento }}</p>
    <p>Endereço: {{ endereco }}</p>
    <p>Cidade: {{ cidade }}</p>
    <p>Estado: {{ estadoDesc }}</p>
    <p>Hobbies: {{ hobbies }}</p>
    <p>Linguagens de programação: {{ linguagensProg }}</p>
    <p>Biografia: {{ biografia }}</p>
  </div>
</template>

<style scoped>
.info {
  padding: 20px;
  border-width: 7px;
  border-style: double;
  border-color: rgba(36, 52, 104, 0.918);
  background-color: rgba(161, 161, 147, 0.815);
}
h1 {
  color: rgba(36, 52, 104, 0.918);
  text-align: center;
}
.ok {
  color: green;
}
.dados {
  padding: 20px;
  border-width: 7px;
  border-style: double;
  border-color: rgba(36, 52, 104, 0.918);
  background-color: rgba(161, 161, 147, 0.815);
}
.erro {
  color: red;
}
</style>
