<template>
  <div id="app">
    <h1 align="center">Валидация формы</h1>
    <Login />
  </div>
</template>

<script>
import Login from './components/Login.vue'
export default {
  name: 'App',
  components: {
    Login
  }
}
</script>

<style>
h1 {
  margin: 50px 0;
}
</style>
