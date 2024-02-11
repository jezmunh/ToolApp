<script setup>
import { RouterLink, RouterView } from 'vue-router'

</script>

<template>
  <div class="app">
  <RouterView />
  </div>
</template>

<style lang="scss" scoped>
.app {
  width: 100%;  
  height: 100dvh;
  background: #344E41;
  display: flex;
  justify-content: center;
  align-items: center;
}
h1 {
    font-size: 40px;    
    color: white;    
}
</style>
