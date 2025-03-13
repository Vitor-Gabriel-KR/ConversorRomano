<template>
  <div>
    <InputField v-model="romanNumber" />
    <br>
    <button @click="convert">Converter</button>
    <OutputField :resultValue="decimalResult" />
  </div>
</template>

<script>
import InputField from './InputField.vue';
import OutputField from './OutputField.vue';

export default {
  components: { InputField, OutputField },
  data() {
    return {
      romanNumber: '',
      decimalResult: ''
    };
  },
  methods: {
    convert() {
      this.decimalResult = this.romanToDecimal(this.romanNumber);
    },
    romanToDecimal(roman) {
      const romanMap = { I: 1, V: 5, X: 10, L: 50, C: 100, D: 500, M: 1000 };
      let total = 0;
      for (let i = 0; i < roman.length; i++) {
        const current = romanMap[roman[i]];
        const next = romanMap[roman[i + 1]];
        if (next && current < next) {
          total -= current;
        } else {
          total += current;
        }
      }
      return total || 'Erro: Entrada inválida';
    }
  }
};
</script>
