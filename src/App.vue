<template>
  <div id="app">
    <img class="logo" src="./assets/logo.svg" />
    <TodoList />
  </div>
</template>

<script setup lang="ts">
  import TodoList from './components/TodoList.vue'
</script>

<style>
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
    width: 80%;
    max-width: 768px;
    margin-left: auto;
    margin-right: auto;
  }
  .logo {
    max-width: 64px;
  }
</style>
