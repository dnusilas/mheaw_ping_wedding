<template>
  <div
    class="flex justify-center items-center min-w-screen min-h-screen relative"
  >
    <div>
      <div id="description" class="relative text-center opacity-0 z-10">
        <div class="text-xs md:text-lg mb-12">
          Tuesday , December
          <span class="text-base md:text-2xl">15</span>th<br />18:00 PM
        </div>

        <div class="text-xs md:text-xl mb-5 md:mb-20">
          At Mellow Garden<br />wine and dine restaurant
        </div>

        <div class="mb-5 md:mb-20">
          <a
            class="btn"
            href="https://goo.gl/maps/hFU98CZ9U4brtnw5A"
            target="_blank"
            >Open Google Map</a
          >
        </div>

        <div class="xl:flex items-center">
          <div class="text-xs xl:text-lg xl:mr-10">Dress Code</div>
          <div class="inline-flex">
            <div class="color color__1 mr-5"></div>
            <div class="color color__2 mr-5"></div>
            <div class="color color__3 mr-5"></div>
            <div class="color color__4"></div>
          </div>
        </div>
      </div>
      <div
        class="hashtag md:w-3/5 xl:w-1/5 -mt-48 md:-mt-56 xl:mt-0 xl:ml-40 relative xl:absolute mx-auto"
      >
        <img class="w-full h-full pb-12" src="/images/S__33873924.png" />
        <p
          class="relative xl:absolute left-0 bottom-0 -mt-48 md:-mt-64 xl:mt-0 xl:pb-32 xl:pl-10 text-xs md:text-base"
        >
          #mmppwedding
        </p>
      </div>
    </div>
  </div>
</template>

<script>
import anime from 'animejs/lib/anime.es'

export default {
  name: 'StepDescription',

  mounted() {
    anime({
      targets: '#description',
      opacity: [0, 1],
      scale: [1.2, 1],
      duration: 2000,
      easing: 'easeInOutQuad',
    })

    anime({
      targets: '.hashtag',
      opacity: [0, 1],
      scale: [1.2, 1],
      delay: 400,
      duration: 2000,
      easing: 'easeInOutQuad',
    })
  },
}
</script>

<style scoped>
.color {
  @apply rounded-full;
  width: 56px;
  height: 56px;
}

@media (max-width: 576px) {
  .color {
    width: 42px;
    height: 42px;
  }
}

.hashtag {
  @apply left-0;
  @apply bottom-0;
  @apply text-center;
  @apply text-sm;
}

.color.color__1 {
  background-color: #183654;
}

.color.color__2 {
  background-color: #deba44;
}

.color.color__3 {
  background-color: #97aeb4;
}

.color.color__4 {
  background-color: #d6dee5;
}

.btn {
  @apply text-xs;
  @apply border;
  @apply border-gray-500;
  @apply px-10;
  @apply py-5;
  @apply inline-block;
  transition: all 0.2s ease-in-out;
}

@media (max-width: 576px) {
  .btn {
    font-size: 16px;
    @apply px-5;
    @apply py-3;
  }
}

.btn:hover {
  box-shadow: 10px 10px 0 #00416b;
  transform: translate(-5px, -5px);
}
</style>
