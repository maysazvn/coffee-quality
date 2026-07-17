<script setup>
import AppHeader from './components/layout/AppHeader.vue/index.js'
import AppFooter from './components/layout/AppFooter.vue/index.js'
</script>

<template>
  <header>
  <AppHeader></AppHeader>
  </header>
  <main>
    <RouterView />
  </main>
  <footer>
  <AppFooter></AppFooter>
  </footer>
</template>

<style scoped>
main, footer, header{
  background-color: white;
}
</style>
