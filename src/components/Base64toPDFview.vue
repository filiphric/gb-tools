<template>
  <textarea v-model="base64Text" ref="input" />
  <object v-if="base64Text.length" type="application/pdf" :data="'data:application/pdf;base64,' + base64Text"></object>
</template>
<script setup lang="ts">
import { ref } from 'vue'
const base64Text = ref('')
</script>
<style scoped>
object {
  width: 600px;
  height: 400px;
}
</style>
