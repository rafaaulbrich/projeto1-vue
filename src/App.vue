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

</script>

<template>
  <form>
    <div class="info">
      <label>Nome:</label>
      <input type="text" v-model="nome" placeholder="Digite seu nome">
      <p>
        <label>Email:</label>
        <input type="email" v-model="email" placeholder="ex.:xxxx@xx.xxx">
      </p>
      <p>
        <label>Senha:</label>
        <input type="password" v-model="senha" placeholder="Digite sua senha">
      </p>
      <p>
        <label>Confirme sua senha:</label>
        <input type="password" v-model="confirmaSenha" placeholder="Confirme sua senha">
      </p>
      <p>
        <label>Data de nascimento:</label>
        <input type="date" v-model="dataNascimento">
      </p>
      <p>
        <label>Endereço:</label>
        <input type="text" v-model="endereco" placeholder="Digite seu endereço">
      </p>
      <p>
        <label>Cidade:</label>
        <input type="string" v-model="cidade" placeholder="Digite seu endereço">
      </p>
      <p>
        <label for="estado">Estado:</label>
        <select v-model="estado">
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
        <input type="text">
      </p>
    </div>
  </form>
</template>

<style scoped>
.info{
  border: 2px solid black;;
  padding: 20px;
}
</style>
