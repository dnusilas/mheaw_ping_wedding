<template>
  <div class="flex justify-center items-center min-w-screen min-h-screen">
    <div class="text-center">
      <div id="step-2-text-1" class="text-sm mb-1 md:mb-10 opacity-0">
        Please Save the Date
      </div>
      <div class="mb-1 md:mb-10">
        <div>
          <Apinya ref="apinya" class="w-2/3 md:w-auto mx-auto" />
        </div>
        <div class="-mt-16 md:-mt-6 pl-16">
          <And ref="and" class="w-16 md:w-auto mx-auto" />
        </div>
        <div class="-mt-16 md:-mt-6">
          <Siphong
            ref="siphong"
            class="w-2/3 md:w-auto mx-auto"
            @fnDrawDone="fillColors"
          />
        </div>
      </div>
      <div id="step-2-text-2" class="opacity-0">are getting married</div>
    </div>
  </div>
</template>

<script>
import anime from 'animejs/lib/anime.es'

import Apinya from './apinya'
import And from './and'
import Siphong from './siphong'

export default {
  name: 'StepIntro',

  components: { Apinya, And, Siphong },

  mounted() {
    this.animateText1()
    this.$refs.apinya.draw()
    setTimeout(() => {
      this.$refs.and.draw()
    }, 1800)
    setTimeout(() => {
      this.$refs.siphong.draw()
    }, 2100)
    setTimeout(() => {
      this.animateText2()
    }, 4000)
  },

  methods: {
    animateText1() {
      anime({
        targets: '#step-2-text-1',
        opacity: [0, 1],
        translateX: [20, 0],
        duration: 2000,
        easing: 'easeInOutQuad',
      })
    },

    animateText2() {
      anime({
        targets: '#step-2-text-2',
        opacity: [0, 1],
        translateX: [20, 0],
        duration: 2000,
        easing: 'easeInOutQuad',
      })
    },

    fillColors() {
      this.$refs.apinya.fill()
      this.$refs.and.fill()
      this.$refs.siphong.fill()
      this.$emit('fnComplete')
    },
  },
}
</script>
