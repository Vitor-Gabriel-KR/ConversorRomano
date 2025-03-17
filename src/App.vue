<template>
  <div class="converter-card">
    <h1>Conversor de Números Romanos</h1>
    <div >
      <Converter />
    </div>
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
  margin: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  background-color: #f8f9fa;
}

#app {
  max-width: 600px;
  width: 100%;
  padding: 2rem;
}

h1 {
  font-size: 2.5rem;
  color: #2c3e50;
  margin-bottom: 1.5rem;
}

.converter-card {
  background: white;
  padding: 2.5rem;
  border-radius: 12px;
  border: 1px solid #e9ecef;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
  width: 100%;
  max-width: 500px;
  margin: 0 auto;
}
</style>