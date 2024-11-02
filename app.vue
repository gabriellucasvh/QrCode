<script setup lang="ts">
import { useHead } from 'nuxt/app'
const inputText = ref('');
useHead({
  htmlAttrs: {
    lang: 'pt-BR'
  },
  title: 'Gerador de QR Codes',
  meta: [
    { name: 'description', content: 'Gerador de QR Codes com Nuxt 3' },
  ],
  link: [
    {
      rel: 'stylesheet',
      href: 'https://fonts.googleapis.com/css2?family=Gabarito:wght@400..900&display=swap'
    }
  ],
})
</script>

<template>
  <main class="main-content">
    <h1>Gerador de QR Code</h1>
    <input type="text" name="Digite o texto" v-model="inputText" placeholder="Digite um link ou texto">
    <QrCode class="qrcode" :value="inputText" :size="300"/>
  </main>
</template>

<style>
.main-content {
  font-family: 'Gabarito', sans-serif;
  margin-top: 50px;
  font-size: 30px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  outline: none;
  padding: 0 16px;
}

input {
  border: 2px solid black;
  border-radius: 10px;
  padding: 10px;
  margin-top: 20px;
  outline: none;
  width: 100%;
  max-width: 400px;
}

.qrcode {
  margin-top: 30px;
  padding: 40px;
  background-color: gainsboro;
  border-radius: 10px;
}

/* Responsividade para telas menores */
@media (max-width: 768px) {
  .main-content {
    font-size: 24px;
  }
  .qrcode {
    padding: 20px;
  }
}

@media (max-width: 480px) {
  .main-content {
    font-size: 20px;
  }
  .qrcode {
    padding: 15px;
  }
}
</style>
