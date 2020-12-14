<template>
  <main
    v-if="clientPosts"
    class="main"
  >
    <h1 class="title text-left">Clients</h1>
    <ul
      v-for="(clientPost, index) in clientPosts"
      :key="index"
      class="articles"
    >
      <nuxt-link
        class="article article--clickable"
        :to="`work/${clientPost.slug}`"
      >
        <h3 class="article-title">{{ clientPost.title }}</h3>
        <div class="mt-4 mb-2">
          <h2 class="inline py-1 px-2 mr-1 bg-accent text-white font-medium rounded-sm dark:bg-accent">{{ clientPost.work_type }}</h2>
          <p class="inline">{{ clientPost.description }}</p>
        </div>
      </nuxt-link>
    </ul>
  </main>
</template>
<script>
export default {
  computed: {
    clientPosts() {
      return this.$store.state.clientPost
    }
  }
}
</script>
