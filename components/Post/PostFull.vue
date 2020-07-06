<template>
  <b-container class="post-full">
    <b-row>
      <b-col cols="12">
        <h1>{{ post.title }}</h1>
      </b-col>
    </b-row>
    <b-row>
      <b-col cols="12">
        <p>{{ post.body }}</p>
      </b-col>
    </b-row>
    <b-row>
      <b-col cols="12">
        <p><n-link to="/">Back to posts</n-link></p>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
  export default {
    props: {
      post: {
        type: Object,
        required: true,
      }
    },
  };
</script>

<style lang="scss" scoped>

</style>
