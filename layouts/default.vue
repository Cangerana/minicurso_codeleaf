<template>
  <div>
    <hero />
    <main class="container mx-auto">
      <nuxt />
    </main>
    <compfooter />
  </div>
</template>

<script>
import compfooter from '~/components/layout/footer.vue'
import hero from '~/components/layout/hero.vue'
export default {
  components: { hero, compfooter },
}
</script>

<style scoped></style>
