<template>
  <section class="web-app-body">
    <div class="container">
      <div class="navigation sidebar"></div>
      <AppBody />
    </div>
  </section>
</template>

<script>
import AppBody from './Containers/Main.vue'

export default {
  name: 'App',
  components: {
    AppBody
  }
}
</script>

<style lang="scss" scoped>
$body-color: #2b2424;
section {
  width: 100%;
  .container {
    width: 1440px;
    background-color: $body-color;
    margin: 0 auto;
    display: flex;
  }
  &.web-app-body {
    .navigation {
      width: 301px;
    }
  }
} 
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
