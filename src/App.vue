<template>
  <div id="app">
   <sajding-main-wrapper/>
  </div>
</template>

<script>
import sajdingMainWrapper from './components/sajding-main-wrapper'

export default {
  name: 'App',
  components: {
    sajdingMainWrapper,
  }
  
}
</script>

<style>
:root{
  --nav-color: #5bc033
}
body {
  margin: 0px;
  padding: 0px;


}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  width: 100%;
  
}
</style>
