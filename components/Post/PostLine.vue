<template>
    <li>
      <h2>{{ post.title }}</h2>
      <p>{{ post.body }}</p>
      <n-link :to="`/post/${post.id}`">les mer</n-link>
    </li>
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
