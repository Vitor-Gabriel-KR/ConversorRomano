<template>
  <div>
    <h3>Resultado:</h3>
    <p>{{ resultValue }}</p>
  </div>
</template>

<script>
export default {
  props: {
    resultValue: String
  }
};
</script>

<style scoped>
h3 {
  color: #6c757d;
  font-size: 1.1rem;
  margin-bottom: 0.5rem;
}

p {
  font-size: 1.4rem;
  font-weight: bold;
  color: #28a745;
  margin: 0;
}
</style>