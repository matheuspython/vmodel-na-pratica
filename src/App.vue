<template>
    <TheHeader />
    <TheMain />
</template>

<script>
import TheHeader from './components/TheHeader.vue';
import TheMain from './components/TheMain.vue';

export default {
  name: 'App',
  components: {
    TheHeader,
    TheMain
}
}
</script>

<style>
*{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
html, body{
  font-family: sans-serif;
}
#app {
  -webkit-font-smoothing: antialiased;
}
</style>
