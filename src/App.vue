<script setup>
  import { ref } from 'vue';

  const nome = ref('');
  const email = ref('');
  const senha = ref('');
  const confirmarSenha = ref('');
  const endereco = ref('');
  const cidade = ref('');
  const estado = ref('');
  const hobbie = ref('');
  const linguagemProgramacao = ref('');
  const biografia = ref('');
  const confirmacao = ref(false);

  function enviarFormulario() {
    if (validarFormulario()) {
      confirmacao.value = true;
    } 
  }

  function validarFormulario() {
    if (nome.value.length < 3) return false;
    if (!email.value.includes('@')) return false;
    if (senha.value != confirmarSenha.value) return false;
    
  }

</script>

<template>
  <form>
    <div>
      <label for="nome">Nome:</label>
      <input type="text" id="nome" v-model.lazy="nome" />
    </div>
    
    <div>
      <label for="email">E-mail:</label>
      <input type="email" id="email" v-model.lazy="email" />
    </div>

    <div>
      <label for="senha">Senha:</label>
      <input type="password" id="senha" v-model.number.lazy="senha" />
    </div>

    <div>
      <label for="confirmarSenha">Confirmar senha:</label>
      <input type="password" id="confirmarSenha" v-model.number.lazy="confirmarSenha" />
    </div>

    <div>
      <label for="endereco">Endereço:</label>
      <input type="text" id="endereco" v-model.number.lazy="endereco" />
    </div>

    <div>
      <label for="cidade">Cidade:</label>
      <input type="text" id="cidade" v-model.number.lazy="cidade" />
    </div>

    <div>
      <label for="estado">Estado:</label>
      <select name="estado" id="estado" v-model.number.lazy="estado">
        <option value="ac">Acre (AC)</option>
        <option value="al">Alagoas (AL)</option>
        <option value="ap">Amapá (AP)</option>
        <option value="am">Amazônas (AM)</option>
        <option value="ba">Bahia (BA)</option>
        <option value="ce">Ceará (CE)</option>
        <option value="df">Distrito Federal (DF)</option>
        <option value="es">Espírito Santo (ES)</option>
        <option value="go">Goiás (GO)</option>
        <option value="ma">Maranhão (MA)</option>
        <option value="mg">Minas Gerais (MG)</option>
        <option value="ms">Mato Grosso do Sul (MS)</option>
        <option value="mt">Mato Grosso (MT)</option>   
        <option value="pa">Pará (PA)</option>
        <option value="pb">Paraíba (PB)</option>
        <option value="pe">Pernambuco (PE)</option>
        <option value="pr">Paraná (PR)</option>
        <option value="pi">Piauí (PI)</option>
        <option value="rj">Rio de Janeiro (RJ)</option>
        <option value="rn">Rio Grande do Norte (RN)</option>
        <option value="ro">Rondônia (RO)</option>
        <option value="rr">Roraima (RR)</option>
        <option value="rs">Rio Grande do Sul (RS)</option>
        <option value="sc">Santa Catarina (SC)</option>
        <option value="se">Sergipe (SE)</option>
        <option value="sp">São Paulo (SP)</option>
        <option value="to">Tocantins (TO)</option>
      </select>
    </div>

    <div>
      <label for="hobbie">Hobbie:</label>
      <input type="text" id="hobbie" v-model.number.lazy="hobbie">
    </div>

    <div>
      <label for="linguagemProgramacao">Linguagem de programação:</label>
      <input type="text" id="linguagemProgramacao" v-model.number.lazy="linguagemProgramacao">
    </div>
    
    <div>
      <label for="biografia">Biografia:</label>
      <textarea name="biografia" id="biografia" cols="30" rows="10" v-model.number.lazy="biografia"></textarea>
    </div>

    <button @click="enviarFormulario">Enviar</button>
    <p v-if="confirmacao">Dados enviados com sucesso:</p>
    <ul v-if="confirmacao">
      <li>Nome: {{ nome }}</li>
      <li>Idade: {{ idade }}</li>
      <li>E-mail: {{ email }}</li>
    </ul>
  
  </form>
</template>

<style scoped>

</style>
