<template>
  <div>
    <label for="roman-input">Digite um Número Romano:</label>
    <input
      id="roman-input"
      type="text"
      v-model="romanNumber"
      @input="updateValue"
      placeholder="Digite um número romano..."
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
    romanNumber: {
      get() {
        return this.modelValue;
      },
      set(value) {
        this.$emit('update:modelValue', value.toUpperCase());
      }
    }
  },
  methods: {
    updateValue() {
      this.$emit('update:modelValue', this.romanNumber);
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
