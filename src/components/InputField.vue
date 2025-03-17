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
  padding: 10px 12px;
  border: 2px solid #ced4da;
  border-radius: 6px;
  font-size: 1rem;
  width: 100%;
  max-width: 300px;
  text-transform: uppercase;
}

input:focus {
  outline: none;
  border-color: #28a745;
}

.hints {
  font-size: 0.75rem;
  color: #6c757d;
  margin-top: 4px;
  display: block;
}
</style>