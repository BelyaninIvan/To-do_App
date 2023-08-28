<script setup>
import HeaderComponent from './components/HeaderComponent.vue'
</script>

<template>
  <header class="header">
    <HeaderComponent/>
  </header>
  <main>

  </main>
  <footer>

  </footer>
</template>

<style scoped>
  .header{
    max-width: 1280px;
    margin: 0 auto;
    padding: 25px 0 75px;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
</style>
