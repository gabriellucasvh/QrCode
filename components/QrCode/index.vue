<template>
  <qrcode-vue :value="value" :size="size" level="H" render-as="svg" />
</template>

<script setup lang="ts">
const props = defineProps({
  value: String
})
import { ref } from 'vue';
import QrcodeVue, { QrcodeCanvas, QrcodeSvg } from 'qrcode.vue';

import { defineProps } from 'vue';
const size = ref(300);
</script>
