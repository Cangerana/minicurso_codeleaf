<template>
  <div>
    <div
      class="article-grid grid-cols-1 lg:grid-cols-2 grid gap-x-8 gap-y-12 my-12"
    >
      <post-preview
        v-for="post in posts"
        :key="`posts-${post.id}`"
        :title="post.title"
        :id="post.id"
        :description="post.description"
        :thumbnail="post.thumbnail"
        :published_at="new Date(post.published_at)"
      />
    </div>
  </div>
</template>

<script>
import postPreview from './post-preview.vue'
export default {
  components: { postPreview },
  props: ['posts'],
}
</script>

<style></style>
