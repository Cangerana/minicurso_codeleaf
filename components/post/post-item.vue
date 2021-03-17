<template>
  <article>
    <div class="flex justify-between">
      <p class="article-title font-semibold text-2xl">{{ title }}</p>
      <div class="article-date">
        <span class="font-semibold">{{ published_at.getDate() }} </span>
        <span>{{
          published_at.toLocaleString('pt-br', { month: 'short' }).slice(0, -1)
        }}</span>
      </div>
    </div>
    <hr />
    <p>{{ content }}</p>
  </article>
</template>

<script>
export default {
  props: {
    id: {
      type: String,
    },
    title: {
      type: String,
      default: 'Title of the Risen Event',
    },
    content: {
      type: String,
      default: 'dahdioawidwaudaw',
    },
    thumbnail: {
      type: Object,
      default: function () {
        return {
          url: '',
          alternativeText: 'Post Thumbnail',
        }
      },
    },
    published_at: {
      type: Date,
    },
  },
}
</script>

<style></style>
