<template>
  <article class="card mb-7 mt-1">
    <h3 class="text-xl mb-2"><NuxtLink to="/posts/4545">Post Title</NuxtLink></h3>
    <p class="text=sm">Use 3 dashes for an em-dash. Use 2 dashes for ranges (ex., "it's allin chapters 12--14"). Three dots ... will be converted to an ellipsis.
Unicode is supported. ☺</p>
    <span class="block text-sm mt-2 mb-2">Created by:Josh</span>
    <itme class="block text-sm text-blue-500"><span class="fas fa-clock"></span>2023-10-01</itme>
    <NuxtLink to="#">Read more</NuxtLink>
  </article>
</template>

<script>
export default {

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