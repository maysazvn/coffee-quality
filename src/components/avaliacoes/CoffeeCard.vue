<script setup>
defineProps(['cafe']);
</script>

 <template>
  <div class="avaliados-cards">
        <div class="esquerda">
          <h2>{{ cafe.nome }}</h2>
          <p class="produtor">Produtor: {{ cafe.produtor }}</p>
          <p class="avaliado">Avaliado em {{ cafe.dtavaliacao }}</p>
        </div>

        <div class="direita">
          <p class="media">Média SCA</p>
          <p class="numero">{{ cafe.media }}</p>
        </div>
      </div>
 </template>

 <style scoped>
 .avaliados-cards {
  display: flex;
  justify-content: space-between;
  border: 1px solid #d6c9c0;
  border-radius: 15px;
  padding: 15px;
  margin-top: 5px;
  align-items: center;
}

h2 {
  font-weight: bold;
  font-size: 1.2rem;
  color: #2b1a13;
  margin-bottom: 5px;
}

p {
  color: #705c53;
}

p.media {
  text-align: center;
}

p.numero {
  font-size: 2rem;
  font-weight: bold;
  text-align: center;
}
</style>
