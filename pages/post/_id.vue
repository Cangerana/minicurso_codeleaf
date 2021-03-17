<template>
  <div class="my-12">
    <post-item
      :id="post.id"
      :title="post.title"
      :content="post.content"
      :thumbnail="post.thumbnail"
      :published_at="new Date(post.published_at)"
    />
  </div>
</template>

<script>
import gql from 'graphql-tag'
import postItem from '~/components/post/post-item.vue'
export default {
  components: { postItem },
  async asyncData({ app, params }) {
    const apolloClient = app.apolloProvider.defaultClient

    const query = gql`
      query post($id: ID!) {
        post(id: $id) {
          id
          title
          description
          content
          published_at
          thumbnail {
            alternativeText
            url
          }
        }
      }
    `
    const variables = {
      id: parseInt(params.id),
    }

    const { data } = await apolloClient.query({ query, variables })

    return {
      post: data.post,
    }
  },
}
</script>

<style></style>
