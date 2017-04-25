<template>
  <div id="app">
    <div class="container">
      <navbar></navbar>
      <router-view></router-view>
      <fil-arianne></fil-arianne>
    </div>
  </div>
</template>

<script>
import Navbar from '@/components/Navbar/Navbar'
import Breadscrumb from '@/components/Breadscrumb/Breadscrumb'

export default {
  name: 'app',
  components: {
    navbar: Navbar,
    filArianne: Breadscrumb,
  }
}
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>