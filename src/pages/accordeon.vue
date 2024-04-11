<script setup lang="ts">
//
import { ref } from 'vue'
const sectionOpen = ref(1)
</script>

<template>
    <p>Accordeon</p>
    <section>
        <button class="text-xl" @pointerdown="sectionOpen = sectionOpen === 1 ? 0 : 1">bouton 1</button>
        <p v-show="sectionOpen ===1">loren...</p>
    </section>
    <section>
        <button class="text-xl" @pointerdown="sectionOpen = sectionOpen === 2 ? 0 : 2">bouton 2</button>
        <p v-show="sectionOpen ===2">loren...</p>
    </section>
    <section>
        <button class="text-xl" @pointerdown="sectionOpen = sectionOpen === 3 ? 0 : 3">bouton 3</button>
        <p v-show="sectionOpen ===3">loren...</p>
    </section>
</template>