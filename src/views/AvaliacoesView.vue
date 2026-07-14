<script setup>
import { cafesAvaliados } from '@/data/CafesAvaliados';
</script>

<template>
<section class="avaliados">
    <h1>Avaliações de cafés</h1>
    <p>blablabla</p>

    <div v-for="cafes in cafesAvaliados" :key="cafes.id" class="avaliadosCards">
        <div>
        <h2>{{ cafes.nome }}</h2>
        <p class="produtor">Produtor: {{ cafes.produtor }}</p>
        <p class="avaliado">Avaliado em {{ cafes.dtavaliacao }}</p>
        </div>

        <div>
            <p class="media">Média SCA</p>
            <p class="numero">{{ cafes.media }}</p>
        </div>
    </div>
</section>
</template>

<style scoped>

.avaliados{
margin: 2vw;
display: flex;
flex-direction: column;
}

.avaliadosCards{
display: flex;
justify-content: space-between;
border: 1px solid #b1b1b1;
border-radius: 15px;
padding: 15px;
margin-top: 5px;
}

h2{
    font-weight: bold;
    font-size: 1.2rem;
}
</style>