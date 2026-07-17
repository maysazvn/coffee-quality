<script setup>
import { ref, computed } from 'vue'
import { cafesAvaliados } from '@/data/CafesAvaliados'

const cafes = ref(cafesAvaliados)

const rankingCafe = computed(() => {
  return [...cafes.value].sort((a, b) => b.media - a.media)
})
//nao ta funcionando quando adiciona outrosla no avaliacoes???
</script>

<template>
  <section class="pagina">
  <section class="inicio">
    <div>
      <h1>Ranking Geral</h1>
    </div>

    <div class="total">
      <span class="txt">Total de cafés avaliados</span>
      <span class="valor">{{ cafes.length }}</span>
    </div>
  </section>

  <section class="ranking">
    <div v-for="(cafe, index) in rankingCafe" :key="cafe.id" class="card-cafe">
      <div class="posicao">
        <span class="numero">{{ index + 1 }}</span>
      </div>

      <div class="cafe-info">
        <div class="icon">☕</div>
        <h2>{{ cafe.nome }}</h2>
        <p class="produtor">Produtor: {{ cafe.produtor }}</p>
      </div>

      <div class="nota">
        <span class="media">{{ cafe.media.toFixed(1) }} </span>
      </div>

      <div class="abrir-detalhes">
        <button class="detalhes">Ver detalhes</button>
      </div>
    </div>
  </section>
  </section>

</template>

<style scoped>
.pagina{
  color: #2b1a13;
  margin: 2vw;
}

.inicio{
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 24px;
}

.inicio h1{
  font-size: 2rem;
  font-weight: bold;
  margin: 0;
  color: #2b1a13;
}

.total{
  display: flex;
  align-items: center;
  gap: 12px;
  background-color: #fdf5ec;
  border: 1px solid #f3e5d8;
  padding: 20px;
  border-radius: 15px;
}

.total.txt{
  font-weight: bold;
  color: #705c53;
  font-size: 0.8rem;
}

.total.valor{
  font-size: 2rem;
  font-weight: bold;
  color: #2b1a13;
}

.ranking{
  display: flex;
  flex-direction: column;
  gap: 10px;
  margin-bottom: 30px;
}

.card-cafe{
  display: grid;
  grid-template-columns: 60px 1.5fr 1fr 120px;
  align-items: center;
  border: 1px solid #dbc7b4;
  border-radius: 10px;
  padding: 15px;
}

.posicao{
  display: flex;
  align-items: center;
}

.numero{
  font-size: 1.5rem;
  font-weight: bold;
  color: #705c53;
}

.cafe-info{
  display: flex;
  align-items: center;
  gap: 15px;
}

.cafe-info h2{
  font-weight: bold;
  margin-bottom: 4px;
  color: #2b1a13;
}

.icon{
  width: 50px;
  font-size: 2.5rem;
  display: flex;
  align-items: center;
  justify-content: center;
}

.produtor{
  color: #705c53;
}

.nota{
  display: flex;
  flex-direction: column;
}

.media{
  font-size: 1.5rem;
  font-weight: bold;
}

.detalhes{
  color: #5c3e35;
  background-color: #f4f0ea;
  border: 1px solid #dcd3cb;
  padding: 10px;
  border-radius: 10px;
  font-weight: 600;
  cursor: pointer;
}
</style>
