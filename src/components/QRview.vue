<template>
  <textarea v-model="qrText" @input="generateQR(qrText)" ref="input" />
  <img :src="QRResult" v-if="qrText?.length" />
</template>
<script setup lang="ts">
import QRCode from 'qrcode'
import { ref, onMounted } from 'vue';

const QRResult = ref()
const input = ref(null)

onMounted(() => {
  // @ts-ignore
  input.value.focus()
})

const generateQR = async(text: string) => {
  if (text.length) {
    QRResult.value = await QRCode.toDataURL(text)
  }
}

const qrText = ref()

</script>

