<script setup>
</script>

<template>
<section class="banner">
<div>
    <p>☕</p>
</div>

<div>
    <h1>Campeonato de Avaliação da Qualidade de Café</h1>

    <hr>

    <p>blablabla</p>
</div>
</section>

<section class="avaliacoes">
<div class="cards">
    <div class="card">
        <h2>Total de cafés avaliados</h2>
        <!-- {{ cafes-avaliados }} -->
          <p>cafés</p>
    </div>
    <div class="card">
        <h2>Café com maior nota</h2>
                <!-- {{ nota }} -->
    </div>
    <div class="card">
        <h2>Ultima avaliacao</h2>
         <!-- {{ ultimo-avaliado }} -->
    </div>
</div>

    <router-link to="/avaliacoes">
        Ver avaliações
    </router-link>

</section>
</template>

<style scoped>

.banner{
    display: flex;
    background-color: rgb(255, 241, 225);
    margin: 2vw;
    border: 1px solid #222;
    padding: 5px;
    border-radius: 10px;
}

.avaliacoes{
    display: flex;
    flex-direction: column;
    justify-content: center;
}

.cards{
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 5px;
    margin: 2vw;
}

.card{
    border: 1px solid #b8b8b8;
    padding: 5px;
    border-radius: 10px;
}


</style>