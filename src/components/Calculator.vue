<template>
  <div class="bg-white rounded-2xl shadow-lg p-6 w-full max-w-sm">
    <div class="mb-4 text-right text-2xl font-mono bg-gray-100 rounded-lg p-3">
      {{ current || "0" }}
    </div>
    <div class="grid grid-cols-4 gap-2">
      <button 
        v-for="btn in buttons" 
        :key="btn" 
        @click="handleClick(btn)"
        class="p-4 text-lg font-semibold rounded-lg shadow-sm bg-gray-200 hover:bg-gray-300 transition"
      >
        {{ btn }}
      </button>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue"

const current = ref("")
const buttons = [
  "7","8","9","/",
  "4","5","6","*",
  "1","2","3","-",
  "0",".","=","+",
  "C"
]

function handleClick(value) {
  if (value === "C") {
    current.value = ""
  } else if (value === "=") {
    try {
      current.value = eval(current.value).toString()
    } catch {
      current.value = "Error"
    }
  } else {
    current.value += value
  }
}
</script>