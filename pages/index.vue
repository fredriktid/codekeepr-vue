<template>
  <div class="container">
    <div>
      <h1>Posts</h1>
      <p v-if="$fetchState.pending">Fetching posts...</p>
      <p v-else-if="$fetchState.error">Error while fetching posts: {{ $fetchState.error.message }}</p>
      <ul v-else>
        <li v-for="post of posts" :key="post.id">
          <PostLine :post="post"></PostLine>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import PostLine from "../components/Post/PostLine";
export default {
  components: {PostLine},
  data () {
    return {
      posts: []
    }
  },
  async fetch () {
    this.posts = await this.$http.$get('https://jsonplaceholder.typicode.com/posts')
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family:
    'Quicksand',
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
