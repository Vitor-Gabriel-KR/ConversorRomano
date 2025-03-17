<template>
  <div>
<<<<<<< HEAD
    <label for="input">Digite um Número Romano ou Decimal:</label>
    <input
      id="input"
      type="text"
      v-model="inputValue"
      @input="updateValue"
      placeholder="Digite um número romano ou decimal..."
=======
    <label for="roman-input">Digite um Número Romano:</label>
    <input
      id="roman-input"
      type="text"
      v-model="romanNumber"
      @input="updateValue"
      placeholder="Digite um número romano..."
>>>>>>> d32e85e6696630a450f59970826488364dd8e6b1
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
<<<<<<< HEAD
    inputValue: {
=======
    romanNumber: {
>>>>>>> d32e85e6696630a450f59970826488364dd8e6b1
      get() {
        return this.modelValue;
      },
      set(value) {
        this.$emit('update:modelValue', value.toUpperCase());
      }
    }
  },
  methods: {
<<<<<<< HEAD
    updateValue(event) {
      this.$emit('update:modelValue', event.target.value.toUpperCase());
      this.$emit('input', event);
=======
    updateValue() {
      this.$emit('update:modelValue', this.romanNumber);
>>>>>>> d32e85e6696630a450f59970826488364dd8e6b1
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
<<<<<<< HEAD
</style>
=======
</style>
>>>>>>> d32e85e6696630a450f59970826488364dd8e6b1
