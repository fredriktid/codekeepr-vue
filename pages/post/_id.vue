<template>
  <div class="container">
    <div>
      <h1 class="title">
        {{ name }}
      </h1>
    </div>
  </div>
</template>

<script>
export default {
  asyncData(context) {
    // called every time before loading the component
    // as the name said, it can be async
    // Also, the returned object will be merged with your data object
    return {name: 'World'}
  },
  fetch() {
    // The `fetch` method is used to fill the store before rendering the page
  },
  head() {
    // Set Meta Tags for this Page
  },
  // and more functionality to discover
}
</script>
