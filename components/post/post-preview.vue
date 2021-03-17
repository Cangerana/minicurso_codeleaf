<template>
  <article class="article-item text-dark flex">
    <div class="article-date">
      <span class="text-xl">
        {{
          published_at.toLocaleString('pt-br', { month: 'short' }).slice(0, -1)
        }}
      </span>
      <hr class="w-4 my-2" />
      <span class="text-4xl font-semibold"> {{ published_at.getDate() }} </span>
    </div>
    <img
      :src="thumbnail.url"
      :alt="thumbnail.alternativeText"
      class="article-thumbnail flex w-64 h-64 object-cover mx-4"
    />
    <div class="article-info flex flex-col justify-between w-full">
      <div>
        <nuxt-link
          tag="a"
          :to="`/post/${id}`"
          class="article-title font-semibold text-2xl mb-4 hover:text-primary transition-colors duration-300 ease-in-out"
        >
          {{ title }}
        </nuxt-link>
        <p class="article-description font-roboto-slab">
          {{ description }}
        </p>
      </div>
      <div>
        <hr class="my-4 border-dark border-opacity-25" />
        <nuxt-link tag="a" :to="`/post/${id}`" class="flex justify-end">
          <span
            class="font-semibold hover:text-primary transition-colors duration-300 ease-in-out"
            >Leia mais</span
          >
          <i class="icon-ic-chevron-right text-2xl text-primary"></i>
        </nuxt-link>
      </div>
    </div>
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
    description: {
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
