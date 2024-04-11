<script setup lang="ts">
//
import { ref } from 'vue'
const sectionOpen = ref(1)
</script>

<template>
    <p>Accordeon</p>
    <section>
        <button class="text-xl" @pointerdown="sectionOpen = sectionOpen === 1 ? 0 : 1">bouton 1</button>
        <p v-show="sectionOpen ===1">Lorem ipsum dolor sit amet consectetur adipisicing elit. Fugiat repudiandae ea sunt deserunt quidem illo aut assumenda atque, aspernatur nulla, tempore esse iusto dolore aliquid animi! Voluptate blanditiis ullam aliquid?</p>
    </section>
    <section>
        <button class="text-xl" @pointerdown="sectionOpen = sectionOpen === 2 ? 0 : 2">bouton 2</button>
        <p v-show="sectionOpen ===2">Lorem ipsum dolor sit amet consectetur adipisicing elit. Omnis dolorum ex repellendus repellat vitae! Deleniti dolore pariatur animi quaerat sequi saepe. Ad similique animi molestias dolorum atque. Itaque, cum fugit!</p>
    </section>
    <section>
        <button class="text-xl" @pointerdown="sectionOpen = sectionOpen === 3 ? 0 : 3">bouton 3</button>
        <p v-show="sectionOpen ===3">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Sit vero voluptatum consectetur perspiciatis cum autem, at inventore animi. Modi exercitationem velit ad porro, inventore amet necessitatibus eos? Doloremque, quisquam harum?</p>
    </section>
</template>