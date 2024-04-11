<script setup lang="ts">
import { onErrorCaptured } from 'vue'
import { ref } from 'vue'
import { RouterLink, RouterView } from 'vue-router/auto'

onErrorCaptured((err, instance, info) => {
  console.error('erreur : ', err, '\ninfo : ', info, '\ncomposant : ', instance)
  return true
})
const menuIsOpen = ref(false)
</script>

<template>
  <header >
    <nav class="bg-sky-950">
      <ul class="flex space-x-80 justify-center">
        <li class="p-4  ">
          <RouterLink to="/" class=" text-emerald-300 underline"> Accueil </RouterLink>
        </li>
        <li class="p-4 ">
          <RouterLink to="/accordeon" class=" text-emerald-300 underline" active-class="text-blue-600 underline"> Accordéon
          </RouterLink>
        </li>
        <li class="p-4">
          <RouterLink to="/boucles" class=" text-emerald-300 underline" active-class="text-blue-600 underline">Boucles
          </RouterLink>
        </li>
        <button @pointerdown="menuIsOpen = !menuIsOpen" aria-controls="mainNav" aria-expanded="true" class="rounded-full border-2 border-red-600 bg-red-300 px-2">menu
          </button>
      </ul>
          
  
    </nav>
  </header>
  
  <!-- nav#mainNav>ul>li*3>a[href="#"]{item $} -->
  <Transition class="transition-transform duration-1000" enter-from-class="-translate-x-full"
    enter-to-class="translate-x-0" leave-active-class="-translate-x-full">
    <nav id="mainNav" v-show="menuIsOpen" class=" w-screen bg-sky-950 text-emerald-300 flex justify-center py-10">
      <ul>
        <li >
          <RouterLink to="/"> Accueil </RouterLink>
        </li>
        <li >
          <RouterLink to="/accordeon"> Accordéon
          </RouterLink>

        </li>
        <li >
          <RouterLink to="/boucles">Boucles
          </RouterLink>
        </li>
      </ul>
    </nav>
  </Transition>


  <RouterView v-slot="{ Component }">
    <Suspense>
      <component :is="Component" />
    </Suspense>
  </RouterView>
</template>