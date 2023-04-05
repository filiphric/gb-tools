<script setup lang="ts">
import { defineProps } from 'vue';

defineProps({
  img: {
    type: String
  }
})

</script>

<template>
  
  <img :src="img" />
</template>


