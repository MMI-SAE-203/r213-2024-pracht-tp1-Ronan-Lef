<script setup lang="ts">
import {ref} from 'vue'
const sectionOpen = ref(1)
console.log('sectionOpen :', sectionOpen.value)
</script>

<template>
  <h1 class="text-2xl">Bonjour monde !</h1>
  <section>
    <button class="text-xl" @pointerdown="sectionOpen = sectionOpen === 1?0:1">bouton 1</button>
    <p v-show="sectionOpen === 1">Lorem ipsum dolor sit, amet consectetur adipisicing elit. Vero, praesentium sit? Culpa consequatur molestiae iure atque temporibus! Rem harum rerum culpa a, voluptatibus consequatur corporis temporibus ipsa, nam voluptatem provident?</p>
  </section>
  <section>
    <button class="text-xl" @pointerdown="sectionOpen = sectionOpen === 2?0:2">bouton 2</button>
    <p v-show="sectionOpen === 2">Officia, iure, recusandae sint labore quaerat in eum magnam eius impedit quos voluptatem aliquid quae velit quod nesciunt nihil similique eos sequi neque necessitatibus cupiditate veritatis! Quasi sunt illum ducimus.</p>
  </section>
  <section>
    <button class="text-xl" @pointerdown="sectionOpen = sectionOpen === 3?0:3">bouton 3</button>
    <p v-show="sectionOpen === 3">Officia numquam ab repellendus natus aut atque quos explicabo. Cumque aspernatur nostrum quam error in sint, omnis architecto debitis accusantium ipsam distinctio sequi. Neque sint impedit temporibus minima culpa quas!</p>
  </section>
</template>
