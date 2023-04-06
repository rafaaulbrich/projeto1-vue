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
const hobbies = ref('')
const linguagensProg = ref([])
const biografia = ref('')
const mostrarDiv = ref(false)

</script>

<template>
  <form @submit.prevent="mostrarDiv =! mostrarDiv">
    <div class="info">
      <h1>Formulário</h1>
      <label>Nome:</label>
      <input type="text" v-model="nome" placeholder="Digite seu nome" required>
      <p>
        <label>Email:</label>
        <input type="email" v-model="email" placeholder="ex.:xxxx@xx.xxx" required>
      </p>
      <p>
        <label>Senha:</label>
        <input type="password" v-model="senha" placeholder="Digite sua senha" minlength="5" required>
      </p>
      <p>
        <label>Confirme sua senha:</label>
        <input type="password" v-model="confirmaSenha" placeholder="Confirme sua senha" required>
      </p>
      <p>
        <label>Data de nascimento:</label>
        <input type="date" v-model="dataNascimento" required>
      </p>
      <p>
        <label>Endereço:</label>
        <input type="text" v-model="endereco" placeholder="Digite seu endereço" required>
      </p>
      <p>
        <label>Cidade:</label>
        <input type="string" v-model="cidade" placeholder="Digite sua cidade" required>
      </p>
      <p>
        <label for="estado">Estado:</label>
        <select v-model="estado" required>
          <option value="Acre">AC</option>
          <option value="Alagoas">AL</option>
          <option value="Amapá">AP</option>
          <option value="Amazonas">AM</option>
          <option value="Bahia">BA</option>
          <option value="Ceará">CE</option>
          <option value="Distrito Federal">DF</option>
          <option value="Espírito Santo">ES</option>
          <option value="Goiás">GO</option>
          <option value="Maranhão">MA</option>
          <option value="Mato Grosso">MT</option>  
          <option value="Mato Grosso do Sul">MS</option>
          <option value="Minas Gerais">MG</option>
          <option value="Pará">PA</option>
          <option value="Paraíba">PB</option>
          <option value="Paraná">PR</option>
          <option value="Pernambuco">PE</option>
          <option value="Piauí">PI</option>
          <option value="Rio de Janeiro">RJ</option>
          <option value="Rio Grande do Norte">RN</option>
          <option value="Rio Grande do Sul">RS</option>
          <option value="Rondônia">RO</option>
          <option value="Roraima">RR</option>
          <option value="Santa Catarina">SC</option>
          <option value="São Paulo">SP</option>
          <option value="Sergipe">SE</option>
          <option value="Tocantins">TO</option>
        </select>
      </p>
      <p>
        <label>Hobbies:</label>
      </p>
      <textarea v-model="hobbies" cols="40" rows="5" placeholder="Digite seus hobbies" required></textarea>
      <p>
        <label>Linguagens de programação:</label>
      </p>
        <input type="checkbox" v-model="linguagensProg" value="JavaScript"> JavaScript  
        <input type="checkbox" v-model="linguagensProg" value="PHP"> PHP 
        <input type="checkbox" v-model="linguagensProg" value="C++"> C++     
        <input type="checkbox" v-model="linguagensProg" value="SQL"> SQL
        <input type="checkbox" v-model="linguagensProg" value="Python"> Python
      <p>
        <label>Biografia:</label>
      </p>
      <p>
        <textarea v-model="biografia" cols="40" rows="5" placeholder="Digite sua biografia" required></textarea>
      </p>
      <button type="submit">Enviar</button>
    </div>
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
    <p>Estado: {{ estado }}</p>
    <p>Hobbies: {{ hobbies }}</p>
    <p>Linguagens de programação: {{ linguagensProg }}</p>
    <p>Biografia: {{ biografia }}</p>
  </div>
</template>

<style scoped>
.info{
  padding: 20px;
  border-width: 7px;
  border-style: double;
  border-color: rgba(36, 52, 104, 0.918);
  background-color:rgba(207, 207, 194, 0.562)
}
h1{
  color: rgba(36, 52, 104, 0.918);
  text-align: center;
}
.ok{
  color: green;;
}
.dados{
  padding: 20px;
  border-width: 7px;
  border-style: double;
  border-color: rgba(36, 52, 104, 0.918);
  background-color:rgba(207, 207, 194, 0.562)
}
</style>
