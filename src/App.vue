<script setup>
import { RouterView } from 'vue-router'
import TodoHeader from './components/TodoHeader.vue';
</script>

<template>

  <TodoHeader/>
  <RouterView />
</template>

<style lang="scss">
  @import url('https://fonts.googleapis.com/css2?family=Encode+Sans+Expanded:wght@100;200;300;400;500;600&family=Poppins:wght@400;600;700;800&family=Prompt:wght@200;300;400;500;600;700;900&family=Roboto:wght@100;300;400;700;900&family=Rubik:wght@300;400;500;600;700;800;900&display=swap');

  * {
    font-family:"Rubik", sans-serif;
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  .container {
    max-width: 100%;
    margin: 0 auto;
  }

</style>


