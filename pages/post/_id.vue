<template>
  <div v-if="$fetchState.pending">Fetching post #{{$route.params.id}}...</div>
  <div v-else>
    <PostFull :post="post"></PostFull>
  </div>
</template>

<script>
import PostFull from "../../components/Post/PostFull";
export default {
  components: {PostFull},
  data () {
    return {
      post: {}
    }
  },
  async fetch() {
    this.post = await this.$http.$get(`https://jsonplaceholder.typicode.com/posts/${this.$route.params.id}`)
  }
}
</script>
