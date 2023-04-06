<template>
  <form>
  <input type="radio" :checked="showView === 'qr'" id="qr" @click="showView = 'qr'" />
  <label for="qr">QR code generator</label>
  <input type="radio" :checked="showView === 'barcode'" id="barcode" @click="showView = 'barcode'" />
  <label for="barcode">Barcode generator</label>
  <input type="radio" :checked="showView === 'base64'" id="base64" @click="showView = 'base64'" />
  <label for="base64">Base64 to PDF</label>
</form>
  <QRview v-if="showView === 'qr'"/>
  <Barcodeview v-if="showView === 'barcode'"/>
  <Base64toPDFview v-if="showView === 'base64'"/>
</template>
<script setup lang="ts">
import QRview from './components/QRview.vue'
import Barcodeview from './components/Barcodeview.vue'
import Base64toPDFview from './components/Base64toPDFview.vue'
import { ref } from 'vue'
const showView = ref('qr')
</script>

