<script setup>
</script>

<template>
<header>
    <div>
        <img src="" alt="logo">
    </div>
    
    <div>
    <ul>
        <li>
                <router-link to="/">Home</router-link>
        </li>
        <li>
    <router-link to="/avaliacoes">Avaliações</router-link>
        </li>
        <li>
    <router-link to="/ranking">Ranking</router-link>
        </li>
    </ul>

        <img src="" alt="foto usuario">
    </div>
</header>
</template>

<style scoped>

header{
    padding: 5px;
    display: flex;
    justify-content: space-between;
}

ul li{
    margin: 2px;
}

ul{
    display: flex;
}



</style>