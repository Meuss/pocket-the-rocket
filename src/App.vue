<script setup>
import Astro from './components/Astro.vue'
import { gsap } from 'gsap'
import { MotionPathPlugin } from 'gsap/MotionPathPlugin'
import { onMounted } from '@vue/runtime-core'
gsap.registerPlugin(MotionPathPlugin)
onMounted(() => {
  gsap.set('#outer-hidden-3', { visibility: 'hidden' })
  gsap.set('#outer-hidden-2', { visibility: 'hidden' })
  gsap.set('#outer-hidden-1', { visibility: 'hidden' })
  gsap.defaults({
    repeat: -1,
    ease: 'linear'
  })
  gsap.to('#Group-531', {
    motionPath: {
      path: '#outer-1',
      align: '#outer-1',
      alignOrigin: [0.5, 0.5]
    },
    duration: 200
  })
  gsap.to('#Vector_39', {
    motionPath: {
      path: '#outer-hidden-3',
      align: '#outer-hidden-3',
      alignOrigin: [0.5, 0.5],
      start: 0.25,
      end: 1.25
    },
    duration: 40
  })
  gsap.to('#Vector_40', {
    motionPath: {
      path: '#outer-hidden-1',
      align: '#outer-hidden-1',
      alignOrigin: [0.5, 0.5],
      start: 0.8,
      end: 1.8
    },
    duration: 50
  })
  gsap.to('#Vector_41', {
    motionPath: {
      path: '#outer-2',
      align: '#outer-2',
      alignOrigin: [0.5, 0.5],
      start: 0.5,
      end: 1.5
    },
    duration: 70
  })
  gsap.to('#Vector_42', {
    motionPath: {
      path: '#outer-4',
      align: '#outer-4',
      alignOrigin: [0.5, 0.5],
      start: 0.4
    },
    duration: 60
  })
  gsap.to('#Vector_45', {
    motionPath: {
      path: '#outer-4',
      align: '#outer-4',
      alignOrigin: [0.5, 0.5],
      start: 0.7,
      end: 1.7
    },
    duration: 60
  })
  gsap.to('#Group-532', {
    motionPath: {
      path: '#outer-hidden-2',
      align: '#outer-hidden-2',
      alignOrigin: [0.5, 0.5],
      start: 0.2,
      end: 1.2
    },
    duration: 57
  })
  gsap.to('#Vector_48', {
    motionPath: {
      path: '#outer-hidden-3',
      align: '#outer-hidden-3',
      alignOrigin: [0.5, 0.5],
      start: 0.1,
      end: 1.1
    },
    duration: 80
  })
  const tl = gsap.timeline({ defaults: { repeat: -1, ease: 'linear' } })
  tl.to(
    '#pocket',
    {
      motionPath: {
        path: '#outer-hidden-3',
        align: '#outer-hidden-3',
        alignOrigin: [0.5, 0.5]
      },
      duration: 80,
      ease: 'linear'
    },
    0
  )
  tl.to('#pocket', { rotate: 360, duration: 6 }, 0)

  const tl2 = gsap.timeline({ repeat: -1 })
  const delay = '+=10'
  tl2.set('#bgpocket', { opacity: 0, repeat: 0 }, 0)
  tl2.set('#bgpocket', { rotate: '0deg', repeat: 0 }, 0)
  tl2.to('#bgpocket', { opacity: 1, duration: 0.1, repeat: 0 }, delay)
  tl2.to('#bgpocket', { opacity: 0, duration: 0.1, repeat: 0 }, '+=0.1')
  tl2.set('#bgpocket', { rotate: '45deg', repeat: 0 })
  tl2.to('#bgpocket', { opacity: 1, duration: 0.1, repeat: 0 }, delay)
  tl2.to('#bgpocket', { opacity: 0, duration: 0.1, repeat: 0 }, '+=0.1')
  tl2.set('#bgpocket', { rotate: '-45deg', repeat: 0 })
  tl2.to('#bgpocket', { opacity: 1, duration: 0.1, repeat: 0 }, delay)
  tl2.to('#bgpocket', { opacity: 0, duration: 0.1, repeat: 0 }, '+=0.1')
})
</script>

<template>
  <Astro />
  <img id="pocket" src="/pocket.png" alt="pocket the rocket" />
  <div id="bgpocket"></div>
</template>

<style>
body {
  margin: 0;
  background-color: #000;
  height: 100vh;
  width: 100vw;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  overflow: hidden;
}
#app {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
svg {
  height: 100%;
}
#pocket {
  width: 80px;
}
#bgpocket {
  position: absolute;
  background-image: url('/bgpocket.png');
  background-size: cover;
  background-position: center center;
  width: 100vw;
  height: 100%;
  opacity: 0;
}
</style>
