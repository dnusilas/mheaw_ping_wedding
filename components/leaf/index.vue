<template>
  <div class="fixed top-0 right-0 z-0">
    <img
      id="leaf1"
      class="leaf fixed top-0 right-0 w-64 md:w-auto"
      src="/images/leaf-1.svg"
      alt=""
    />
    <img
      id="leaf2"
      class="leaf fixed top-0 right-0 w-64 md:w-auto"
      src="/images/leaf-2.svg"
      alt=""
    />
  </div>
</template>

<script>
import anime from 'animejs/lib/anime.es'

export default {
  mounted() {
    anime({
      targets: '#leaf1',
      opacity: [0, 1],
      rotate: [5, -1],
      delay: 100,
      duration: 2000,
      easing: 'easeInOutQuad',
    })
    anime({
      targets: '#leaf2',
      opacity: [0, 1],
      rotate: [10, -1],
      delay: 500,
      duration: 2000,
      easing: 'easeInOutQuad',
      complete: () => {
        anime({
          targets: '#leaf1',
          rotate: [-1, 1],
          duration: 2000,
          easing: 'easeInOutQuad',
          loop: true,
          direction: 'alternate',
        })
        anime({
          targets: '#leaf2',
          rotate: [-1, 2],
          delay: 800,
          duration: 2000,
          easing: 'easeInOutQuad',
          loop: true,
          direction: 'alternate',
        })
      },
    })
  },
}
</script>

<style scoped>
.leaf {
  transform-origin: 100% 0%;
}
</style>
