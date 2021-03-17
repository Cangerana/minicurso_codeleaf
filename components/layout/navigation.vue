<template>
  <nav class="bg-dark bg-opacity-50 relative">
    <div class="container flex justify-between items-center mx-auto py-4">
      <nuxt-link
        tag="a"
        to="/"
        class="flex items-center font-roboto-slab text-light text-2xl"
      >
        <img src="/img/codeleaf.svg" alt="Code Leaf Logo" class="h-10 mr-4" />
        Code Leaf
      </nuxt-link>
      <ul class="flex">
        <li class="mr-4">
          <nuxt-link tag="a" to="/" class="text-xl text-light cursor-pointer">
            Home
          </nuxt-link>
        </li>
        <li>
          <nuxt-link
            tag="a"
            to="/artigo/contato"
            class="text-xl text-light cursor-pointer"
          >
            Docs
          </nuxt-link>
        </li>
      </ul>
    </div>
  </nav>
</template>

<script>
export default {}
</script>

<style></style>
