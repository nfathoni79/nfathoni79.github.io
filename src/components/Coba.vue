<script setup>
import { onMounted } from 'vue'
import anime from 'animejs/lib/anime.es.js'

const animate = () => {
  anime.timeline({ loop: true })
    .add({
      targets: '.line',
      opacity: [0.5, 1],
      scaleX: [0, 1],
      easing: 'easeInOutExpo',
      duration: 700,
    })
    .add({
      targets: '.line',
      duration: 600,
      easing: 'easeInOutExpo',
      translateY: (el, i) => (-0.8 + 0.8*2*i) + 'em',
    })
    .add({
      targets: '.letters',
      opacity: [0, 1],
      translateX: [
        (el, i) => (0.5 + -0.5*2*i) + 'em',
        0,
      ],
      easing: 'easeOutExpo',
      duration: 600,
    })
}

onMounted(() => {
  animate()
})
</script>

<template>
  <div class="flex items-center justify-center min-h-screen">
    <div class="inline-block relative
      text-5xl md:text-6xl font-bold text-blue-50">
      <span class="line absolute left-0 top-1/2 -translate-y-1/2
        h-1 w-full bg-blue-50 origin-center"></span>
      <span class="letters inline-block">Coming</span>
      <span class="letters inline-block ml-2">Soon</span>
      <span class="line absolute left-0 top-1/2 -translate-y-1/2
        h-1 w-full bg-blue-50 origin-center"></span>
    </div>
  </div>
</template>