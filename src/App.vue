<script setup lang="ts">
import { onErrorCaptured } from 'vue'
import { RouterLink, RouterView } from 'vue-router/auto'
import {ref} from 'vue'
 const menuIsOpen = ref(false)

onErrorCaptured((err, instance, info) => {
  console.error('erreur : ', err, '\ninfo : ', info, '\ncomposant : ', instance)
  return true
})

</script>

<template>
  <button
    @pointerdown="menuIsOpen = !menuIsOpen"
    aria-controls="mainNav"
    aria-expanded="true"
    class="rounded-full border-2 border-indigo-600 bg-indigo-300 px-2"
  >
    menu
  </button>
  <transition
  class="transition-transform duration-1000"
    enter-from-class="-translate-x-full"
    enter-to-class="translate-x-0"
    leave-active-class="-translate-x-full">
  <nav v-show="menuIsOpen" id="mainNav">
    <ul>
      <li><RouterLink to="/" class="text-red-500 underline"> Accueil </RouterLink></li>
      <li><RouterLink to="/accordeon" class="text-red-500 underline"> Accordeon </RouterLink></li>
      <li><RouterLink to="/boucleSurDonnees" class="text-red-500 underline"> Boucle </RouterLink></li>
      <li><RouterLink to="/aspectMenu" class="text-red-500 underline">Aspect Menu </RouterLink></li>
    </ul>
  </nav>
  </transition>
  <header>
    <nav>
      <ul>
        <li>
        </li>
      </ul>
    </nav>
  </header>
  <RouterView v-slot="{ Component }">
    <Suspense>
      <component :is="Component" />
    </Suspense>
  </RouterView>
</template>
