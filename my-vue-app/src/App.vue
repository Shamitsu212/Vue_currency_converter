<script setup lang="ts">
import ConverterForm from './components/features/ConverterForm.vue';


</script>

<template>
  
  <main class="Page">
    <ConverterForm />
  </main>

</template>

<style scoped>
.Page{
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;

  width: 100vw;
  height: 100vh;
}
</style>
