<template>
  <div class="relative">
    <div class="relative z-20">
      <nuxt />
    </div>
    <div class="fixed top-0 left-0 w-screen h-screen">
      <img id="bg" class="w-full h-full object-contain" src="/images/bg.svg" />
    </div>
  </div>
</template>

<script>
export default {
  mounted() {},
}
</script>
