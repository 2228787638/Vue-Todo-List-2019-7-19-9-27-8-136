<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <!--<HelloWorld msg="Welcome to Your Vue.js App"/>-->
    <Inputs></Inputs>
    <Item></Item>
  </div>
</template>

<script>
import Item from "./components/Item";
import Inputs from "./components/Inputs";
export default {
  name: 'app',
  components: {
      Inputs,
      Item
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
