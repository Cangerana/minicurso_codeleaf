<template>
  <div>
    <post-list :posts="posts" />
  </div>
</template>

<script>
import postList from '~/components/post/post-list.vue'
import gql from 'graphql-tag'
export default {
  components: { postList },
  async asyncData({ app, params }) {
    const limit = 4
    const start = parseInt(params.page || 0)

    const apolloClient = app.apolloProvider.defaultClient
    const query = gql`
      query Post($limit: Int, $start: Int) {
        posts(limit: $limit, start: $start) {
          id
          title
          description
          published_at
          thumbnail {
            url
            alternativeText
          }
        }
      }
    `
    const variables = {
      limit: limit,
      start: start,
    }

    const { data } = await apolloClient.query({ query, variables })

    return {
      posts: data.posts,
    }
  },
}
</script>

<style></style>
