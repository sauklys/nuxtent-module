<template>
<div>
    <h1>{{ post.title }}</h1>
		<div v-html="post.body" />
</div>
</template>

<script>
export default {
  async asyncData ({ app, route, payload }) {
    return {
      post: payload || await app.$content('/').get(route.path)
    }
  }
}
</script>
