<template>
  <div class="flex justify-center items-center min-w-screen min-h-screen">
    <span id="visitor" class="opacity-0">To {{ visitor }}</span>
  </div>
</template>

<script>
import anime from 'animejs/lib/anime.es'

export default {
  name: 'StepInvitation',

  props: {
    visitor: {
      type: String,
      default: '',
    },
  },

  mounted() {
    anime({
      targets: '#visitor',
      opacity: [0, 1],
      scale: [1.2, 1],
      delay: 1000,
      duration: 2000,
      easing: 'easeInOutQuad',
      complete: () => {
        this.$emit('fnComplete')
      },
    })
  },
}
</script>
