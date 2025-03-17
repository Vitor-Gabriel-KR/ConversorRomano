<template>
  <div id="app">
    <h1>Conversor de Números Romanos</h1>
    <Converter />
  </div>
</template>

<script>
import Converter from './components/Converter.vue';

export default {
  components: { Converter }
};
</script>

<style>
body {
  font-family: Arial, sans-serif;
  text-align: center;
}
</style>