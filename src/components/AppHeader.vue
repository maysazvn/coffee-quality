<script setup></script>

<template>
  <header>
    <div class="logo">
      <span>LOGO</span>
    </div>

    <div class="nav-links">
      <nav>
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
      </nav>

      <span>👤</span>
    </div>
  </header>
</template>

<style scoped>
header {
  padding: 15px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-bottom: 1px solid #f0e6df;
}

.logo{
  font-weight: bold;
  color: #3e2723;
  font-size: 1.5rem;
}

.nav-links {
  display: flex;
  align-items: center;
  gap: 25px;
}

ul {
  display: flex;
  list-style: none;
  margin: 0;
  padding: 0;
  gap: 20px;
}

ul li {
  margin: 2px;
}

ul li a {
  text-decoration: none;
  color: #3e2723;
}

</style>
