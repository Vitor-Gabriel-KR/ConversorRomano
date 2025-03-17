<template>
  <div>
    <InputField v-model="inputValue" @input="convertAutomatically" />
    <br>
    <button @click="convert">Converter</button>
    <OutputField :resultValue="result" />
  </div>
</template>


<script>
import InputField from './InputField.vue';
import OutputField from './OutputField.vue';

export default {
  components: { InputField, OutputField },
  data() {
    return {
      inputValue: '',
      result: ''
    };
  },
  methods: {
    convert() {
      if (this.isRoman(this.inputValue)) {
        this.result = this.romanToDecimal(this.inputValue);
      } else if (this.isDecimal(this.inputValue)) {
        const decimal = parseInt(this.inputValue, 10);
        if (decimal > 10000) {
          this.result = 'Erro: O limite de 10.000 foi atingido.';
        } else {
          this.result = this.decimalToRoman(decimal);
        }
      } else {
        this.result = 'Erro: Entrada inválida';
      }
    },
    convertAutomatically() {
      this.convert();
    },
    isRoman(str) {
      return /^[IVXLCDM]+$/i.test(str);
    },
    isDecimal(str) {
      return /^\d+$/.test(str);
    },
    romanToDecimal(roman) {
      const romanMap = { I: 1, V: 5, X: 10, L: 50, C: 100, D: 500, M: 1000 };
      let total = 0;
      for (let i = 0; i < roman.length; i++) {
        const current = romanMap[roman[i].toUpperCase()];
        const next = romanMap[roman[i + 1]?.toUpperCase()];
        if (next && current < next) {
          total -= current;
        } else {
          total += current;
        }
      }
      return total || 'Erro: Entrada inválida';
    },
    decimalToRoman(decimal) {
      const val = [
        1000, 900, 500, 400,
        100, 90, 50, 40,
        10, 9, 5, 4,
        1
      ];
      const syms = [
        "M", "CM", "D", "CD",
        "C", "XC", "L", "XL",
        "X", "IX", "V", "IV",
        "I"
      ];
      let num = parseInt(decimal, 10);
      if (isNaN(num)) {
        return 'Erro: Entrada inválida';
      }
      let result = '';
      for (let i = 0; i < val.length; i++) {
        while (num >= val[i]) {
          result += syms[i];
          num -= val[i];
        }
      }
      return result;
    }
  }
};
</script>

<style scoped>
.converter-container {
  display: flex;
  flex-direction: column;
  gap: 1.2rem;
  width: 100%;
}

button {
  background: #28a745;
  color: white;
  border: none;
  padding: 12px 24px;
  border-radius: 6px;
  font-size: 1rem;
  cursor: pointer;
  transition: background 0.3s ease;
  width: 100%;
  font-weight: 600;
}

button:hover {
  background: #218838;
}

.error-message {
  color: #dc3545;
  font-size: 0.9rem;
  margin-top: 0.5rem;
  text-align: center;
}
</style>