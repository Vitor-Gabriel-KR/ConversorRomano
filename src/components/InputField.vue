<template>
  <div>
    <label for="input">Digite um Número Romano ou Decimal:</label>
    <input
      id="input"
      type="text"
      v-model="inputValue"
      @input="updateValue"
      placeholder="Digite um número romano ou decimal..."
    />
  </div>
  <label class="hints">Números romanos podem ser: I, V, X, L, C, D, M</label>
</template>

<script>
export default {
  props: {
    modelValue: String
  },
  computed: {
    inputValue: {
      get() {
        return this.modelValue;
      },
      set(value) {
        this.$emit('update:modelValue', value.toUpperCase());
      }
    }
  },
  methods: {
    updateValue(event) {
      this.$emit('update:modelValue', event.target.value.toUpperCase());
      this.$emit('input', event);
    }
  }
};
</script>

<style scoped>
input {
  padding: 8px;
  font-size: 13px;
  width: 200px;
  text-transform: uppercase;
}
.hints {
  font-size: 12px;
  color: #888;
  margin-top: 4px;
  display: block;
}
</style>