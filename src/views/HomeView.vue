<script setup></script>

<template>
  <section class="banner">
    <div class="banner-icon">
      <span>☕</span>
    </div>

    <div class="banner-texto">
      <h1>Campeonato de Avaliação da Qualidade de Café</h1>
      <hr />
      <p>Avalie, compare e descubra os melhores cafés especiais.</p>
    </div>
  </section>

  <section class="avaliacoes">
    <div class="cards-grid">
      <div class="card">
        <div class="icon">👥</div>

        <div class="card-info">
          <h2>Total de cafés avaliados</h2>
          <!-- {{ cafes-avaliados }} -->
          <p>Cafés</p>
        </div>
      </div>
      <div class="card">
        <div class="icon">🏆</div>

        <h2>Café com maior nota</h2>
        <!-- {{ nota }} -->
      </div>
      <div class="card">
        <div class="icon">🕒</div>

        <h2>Ultima avaliacao</h2>
      </div>
    </div>

    <router-link to="/avaliacoes" class="btn-avaliar"> <span>📋</span> Ver avaliações </router-link>
  </section>
</template>

<style scoped>
.banner {
  display: flex;
  background-color: #fdf5ec;
  margin: 2vw;
  border: 1px solid #f3e5d8;
  padding: 30px;
  border-radius: 10px;
  gap: 30px;
}

.banner-icon{
  font-size: 4.5rem;
  display: flex;
  align-items: center;
  justify-content: center;
}

.banner-texto h1 {
  font-size: 1.8rem;
  font-weight: bold;
  margin-bottom: 10px;
  color: #2b1a13;
}

hr{
  width: 60px;
  margin-bottom: 15px;
border-top: 2px solid #d7ccc8;
}

.banner-texto p {
  color: #705c53;
}

.avaliacoes {
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.cards-grid {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  gap: 15px;
  margin: 2vw;
}

.card {
  border: 1px solid #b8b8b8;
  padding: 15px;
  border-radius: 10px;
}

.card h2{
  font-weight: bold;
  color: #2b1a13;
  margin: 10px 0;
}

.icon{
  display: flex;
  align-items: center;
  justify-content: center;
  width: 48px;
  height: 48px;
  border-radius: 50%;
  font-size: 1.5rem;
  background-color: #fdf2e9;
}

.btn-avaliar {
  align-items: center;
  gap: 8px;
  background-color: #5c3826; /* Marrom café escuro */
  color: #ffffff;
  padding: 12px 30px;
  border-radius: 8px;
  text-decoration: none;
  width: 15%;
  margin: 0 auto;
}

/* paleta:
#2b1a13 Marrom escuro para letras
#705c53 Marrom para letras mais claras
#5c3826 Marrom café escuro
#fdf5ec Creme de fundo
#f3e5d8 Creme bordas
#fdf2e9 Creme de fundo 2 */
</style>
