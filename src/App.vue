<script setup lang="ts">
import HelloWorld from './components/HelloWorld.vue'
import QRCode from 'qrcode'
import { ref } from 'vue';

const result = ref()

const generateQR = async(text: string) => {
  try {
    result.value = await QRCode.toDataURL(text)
  } catch (err) {
    console.error(err)
  }
}

const qrText = ref()

</script>

<template>
  <h1>QR code generator</h1>
  <textarea v-model="qrText" />
  <button @click="generateQR(qrText)">Generate QR</button>
  <HelloWorld :img="result" />
</template>
<style scoped>
textarea, button {
  display: block;
  margin: 0 auto;
  margin-top: 10px;
}
</style>