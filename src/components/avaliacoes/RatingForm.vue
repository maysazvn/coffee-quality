<script setup>
import { ref, computed } from 'vue';
import { cafesAvaliados } from '@/data/CafesAvaliados'

const cafes = ref(cafesAvaliados);

defineEmits(['salvar']);

const nome = ref('');
const produtor = ref('');
const aroma = ref(0);
const sabor = ref(0);
const acidez = ref(0);
const corpo = ref(0);
const finalizacao = ref(0);

const calculoMedia = computed(() => {
const soma = aroma.value + sabor.value + acidez.value + corpo.value + finalizacao.value;
const resultado = soma/5;
return resultado.toFixed(1);
});

function limparFormulario() {
  nome.value = '';
  produtor.value = '';
  aroma.value = 0;
  sabor.value = 0;
  acidez.value = 0;
  corpo.value = 0;
  finalizacao.value = 0;
}

function salvarAvaliacao(){
  if(!nome.value || !produtor.value){
    alert(`Por favor preencha os dados.`);
    return;
  }

const novosCafesAvaliados =
  {
    id: cafes.value.length + 1,
    nome: nome.value,
    produtor: produtor.value,
    dtavaliacao: new Date().toLocaleString('pt-BR'),
    media: calculoMedia.value
  }

cafes.value.push(novosCafesAvaliados);
limparFormulario();
}
</script>

<template>

 <form @submit.prevent="salvarAvaliacao">
        <div class="infos">
          <div class="info-item">
            <label>Nome do café</label>
            <input type="text" v-model="nome" placeholder="Bourbon Amarelo"/>
          </div>
          <div class="info-item">
            <label>Nome do produtor</label>
            <input type="text" v-model="produtor" placeholder="Fazendo Boa Vista"/>
          </div>
        </div>

        <h3>Notas SCA (0 a 10)</h3>
        <div class="notas">
          <div class="nota-item">
            <label>👃 Aroma</label>
            <input type="number" v-model="aroma" min="0" max="10" step="0.1" value="0" />
          </div>
          <div class="nota-item">
            <label>☕ Sabor</label>
            <input type="number" v-model="sabor" min="0" max="10" step="0.1" value="0" />
          </div>
          <div class="nota-item">
            <label>🍋 Acidez</label>
            <input type="number" v-model="acidez" min="0" max="10" step="0.1" value="0" />
          </div>
          <div class="nota-item">
            <label>🔗 Corpo</label>
            <input type="number" v-model="corpo" min="0" max="10" step="0.1" value="0" />
          </div>
          <div class="nota-item">
            <label>🥃 Finalização</label>
            <input type="number" v-model="finalizacao" min="0" max="10" step="0.1" value="0" />
          </div>
        </div>

        <div class="media">
          <span class="titulo">Média SCA (calculada automaticamente)</span>
          <span class="valor">{{ calculoMedia }}</span>
        </div>

        <div class="botoes">
          <button type="reset" class="limpar" @click="limparFormulario">Limpar</button>
          <button type="submit" class="enviar">Enviar</button>
        </div>
      </form> 
</template>

<style scoped>

.infos{
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 16px;
  margin-bottom: 16px;
}

.info-item{
  display: flex;
  flex-direction: column;
}

.infos label{
color: #705c53;
font-weight: 600;
  margin-bottom: 6px;
}

.infos input{
  border: 1px solid  #d6c9c0;
  border-radius: 10px;
  padding: 10px;
  color: #3e2723;
  background-color: #fdfdfd;
}

h3{
  font-weight: bold;
  color: #3e2723;
  margin: 20px 0 10px 0;
}

.notas{
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr 1fr;
  gap: 10px;
  margin-bottom: 20px;
}

.nota-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  border-radius: 10px;
  padding: 10px;
}

.nota-item label{
  color: #705c53;
  margin-bottom: 6px;
}

.nota-item input {
  border: 1px solid  #d6c9c0;
  border-radius: 10px;
  padding: 5px;
  text-align: center;
  font-weight: bold;
  color: #3e2723;
}

div.media{
  display: flex;
  flex-direction: column;
    align-items: center;
  justify-content: center;
  background-color: #fdf5ec;
  border: 1px solid  #d6c9c0;
  border-radius: 10px;
  padding: 15px;
}

div.media .titulo{
  color: #705c53;
  font-weight: bold;
}

div.media .valor{
  font-size: 2rem;
  font-weight: bold;
  color: #2e7d32;
  margin-top: 5px;
}

.botoes{
  display: flex;
  justify-content: center;
  gap: 10px;
  margin: 10px;
}

.limpar,
.enviar{
  align-items: center;
  gap: 10px;
  padding: 10px 20px;
  border-radius: 10px;
  font-weight: bold;
}

.limpar{
  background-color: #ffffff;
  color: #705c53;
  border: 1px solid  #d6c9c0;
}

.limpar:hover{
  background-color: #fcf9f6;
  cursor: pointer;
}

.enviar{
  background-color: #5c3826;
  color: #ffffff;
  border: none;
}

.enviar:hover{
  background-color: #4a2c1d;
  cursor: pointer;
}
</style>