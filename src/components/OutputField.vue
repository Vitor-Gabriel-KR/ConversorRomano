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
p {
  font-size: 20px;
  font-weight: bold;
}
</style>
