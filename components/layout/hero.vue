<template>
  <header class="relative hero-header">
    <navigation class="absolute top-0 z-10" />
    <div class="absolute top-0 flex items-center justify-around h-full w-full">
      <h1
        class="text-6xl text-light tracking-widest font-semibold uppercase text-center"
      >
        CODE LEAF
      </h1>
    </div>
  </header>
</template>

<script>
import navigation from './navigation.vue'
export default {
  components: { navigation },
}
</script>

<style scoped>
.hero-header {
  height: 500px;
  background-image: url(/img/sid-balachandran-cUpp1gAEtiU-unsplash.jpg);
  background-position: center;
  background-size: cover;
}
</style>
