<template>
  <div id="app">
    <FormInfo />
  </div>
</template>

<script>
  import FormInfo from "./components/FormInfo";

export default {
  name: 'App',
  components: {
    FormInfo
  },
}
</script>

<style>
  :root {
  }

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /*text-align: center;*/
  color: #2c3e50;
  margin: auto;
  max-width: 600px;
}
</style>
