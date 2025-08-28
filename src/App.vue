<template>
  <div class="min-h-screen flex flex-col justify-between bg-gray-100">
    <main class="flex flex-1 items-center justify-center p-4">
      <Calculator />
    </main>
    <Footer />
  </div>
</template>

<script setup>
import Calculator from "./components/Calculator.vue"
import Footer from "./components/Footer.vue"
</script>