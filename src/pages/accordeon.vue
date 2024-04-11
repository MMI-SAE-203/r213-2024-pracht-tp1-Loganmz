<script setup lang="ts">
//
import { ref } from 'vue'
const sectionOpen = ref(1)
</script>

<template>
    <p>Onglet 1</p>
    <section>
    <button class="text-xl" @pointerdown="sectionOpen = sectionOpen === 1 ? 0 : 1">bouton 1</button>
    <p v-show="sectionOpen ===1">loren...</p>
  </section>
</template>