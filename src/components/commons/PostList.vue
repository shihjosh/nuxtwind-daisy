<template>
  <article class="card mb-7 mt-1">
    <h3 class="text-xl mb-2"><nuxt-link :to="'/posts/' + post.id">{{ post.title }}</nuxt-link></h3>
    <p class="text=sm">{{ post.content.substring(0,50) }}</p>
    <span class="block text-sm mt-2 mb-2">Created by: {{ post.author }}</span>
    <itme class="block text-sm text-blue-500"><span class="fas fa-clock"></span>{{ post.created_at }}</itme>
    <NuxtLink  :to="'/posts/' + post.id">Read more</NuxtLink>
  </article>
</template>

<script>
const props = {
  post: {
    type: Object,
    required: true
  }
}

export default {
  props,
}
</script>

<style lang="css" scoped>
a {
   @apply text-green-600 underline;

   font-size: 15px;
}

a:hover {
   @apply text-green-800 font-bold;
}

h1, h2, h3, h4, h5, h6 {
  @apply text-gray-500;
}

</style>