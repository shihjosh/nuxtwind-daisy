<template>
  <article>
    <h1>{{ page.title }}</h1>
    <nuxt-content :document="page" />
  </article>
</template>

<script>
export default {
  async asyncData({ $content }) {
    const page = await this.$content("articles")
      .sortBy("desc")
      .limit(5)
      .fetch();
    return { page };
  },
}
</script>

<style></style>
