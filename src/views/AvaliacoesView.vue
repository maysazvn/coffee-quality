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

        <div class="dois">
            <p class="media">Média SCA</p>
            <p class="numero">{{ cafes.media }}</p>
        </div>
    </div>

    <div class="sua-avaliacao">
        <!-- v-if eu acho -->
         <div>
☕
         </div>
         <div>
Nenhum café avaliado ainda.
         </div>

    </div>
</section>

<section>
    <h1></h1>
</section>
</template>

<style scoped>

h1{
    font-weight: bold;
    font-size: 2rem;
}

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
align-items: center;
}

.sua-avaliacao{
    display: flex;
justify-content: center;
border: 1px solid #b1b1b1;
border-radius: 15px;
padding: 15px;
margin-top: 5px;
align-items: center;
gap: 10px;
}

h2{
    font-weight: bold;
    font-size: 1.2rem;
    color: black;
}

p{
    color:#4e4e4e;
}

p.media{
    text-align: center;
}

p.numero{
font-size: 2rem;
font-weight: bold;
text-align: center;

}
</style>