<script setup>
import { cafesAvaliados } from '@/data/CafesAvaliados'
import { ref } from 'vue';
import CoffeeCard from '@/components/avaliacoes/CoffeeCard.vue';
import RatingForm from '@/components/avaliacoes/RatingForm.vue';

const cafes = ref(cafesAvaliados);


function adicionarNovoCafe(dadosForm){
const novosCafesAvaliados =
  {
    id: cafes.value.length + 1,
    nome: dadosForm.nome.value,
    produtor: dadosForm.produtor.value,
    dtavaliacao: new Date().toLocaleString('pt-BR'),
    media: dadosForm.calculoMedia.value
  }

  cafes.value.push(novosCafesAvaliados)
}

</script>

<template>
  <div class="pagina">
    <section class="avaliados">
      <h1>Avaliações de cafés</h1>
      <p>Veja os cafés já avaliados e adicione uma nova avaliação.</p>

<CoffeeCard v-for="cafe in cafes" :key="cafe.id" :cafe="cafe"></CoffeeCard>

    </section>

    <section class="forms">
      <h2>Nova Avaliação</h2>

      <RatingForm @salvar="adicionarNovoCafe"></RatingForm>

    </section>
  </div>
</template>

<style scoped>
.pagina{
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 30px;
  margin: 2vw;
}

.avaliados {
  margin: 2vw;
  display: flex;
  flex-direction: column;
}

h1 {
  font-weight: bold;
  font-size: 2rem;
  color: #2b1a13;
  margin-bottom: 5px;
}

.avaliados p{
color: #705c53;
margin-bottom: 20px;
}

.forms{
   border: 1px solid #d6c9c0;
  border-radius: 15px;
  padding: 50px;
}

</style>
