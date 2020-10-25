<template>
  <div @click="nextStep">
    <div class="relative z-10">
      <template v-if="step === 1">
        <Invitation :visitor="visitor" @fnComplete="onAnimated" />
      </template>
      <template v-else-if="step === 2">
        <Intro @fnComplete="onAnimated" />
      </template>
      <template v-else>
        <Description />
      </template>
    </div>
    <Leaf />
  </div>
</template>

<script>
import Invitation from '@/components/step/1-invitation'
import Intro from '@/components/step/2-intro'
import Description from '@/components/step/3-description'
import Leaf from '@/components/leaf'

export default {
  name: 'IndexPage',

  components: { Invitation, Intro, Description, Leaf },

  data() {
    return {
      step: 1,
      isAnimating: true,

      visitor: this.$route.query.visitor || '',
    }
  },

  methods: {
    nextStep() {
      if (this.isAnimating) return
      if (this.step === 3) return

      this.isAnimating = true
      this.step++
    },

    onAnimated() {
      this.isAnimating = false
    },
  },
}
</script>
