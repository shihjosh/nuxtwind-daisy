<template>
  <div>
    <h1 class="text-3xl mb-4">Latest Posts</h1>

    <section>  
        <PostList />
        <PostList />
        <PostList />
        <PostList />
    </section>

  </div>
</template>

<script>
import PostList from '~/components/commons/PostList';
export default {
    components: {
        PostList,
  },
}
</script>

<style lang="css" scoped>

h1, h2, h3, h4, h5, h6 {
  @apply text-gray-500;
}

</style>