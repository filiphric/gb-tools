<template>
  <textarea v-model="barcodeText" @input="generateBarcode(barcodeText)" ref="input" />
  <canvas ref="barcodeRef" v-if="barcodeText?.length" />
</template>
<script setup lang="ts">
import { ref, onMounted } from 'vue';
import JsBarcode from 'jsbarcode';

const barcodeText = ref()
const input = ref(null)
const barcodeRef = ref(null);

const generateBarcode = async(text: string) => {
  if (text.length) {
    JsBarcode(barcodeRef.value, text, {
      format: 'code39',
      displayValue: true
    });
  }
} 

onMounted(() => {
  // @ts-ignore
  input.value.focus()
})
</script>

<style scoped>
canvas {
  max-width: 400px;
}
</style>

