<template>
  <article class="card mb-7 mt-1">
    <h1 class="text-3xl mb-2 text-center"><NuxtLink to="/posts/4545">Post Title</NuxtLink></h1>
    <p >Use 3 dashes for an em-dash. Use 2 dashes for ranges (ex., "it's allinchapters 12--14"). Three dots ... will be converted to an ellipsis.Unicode is supported. ☺ Use 3 dashes for an em-dash. Use 2 dashes for ranges (ex., "it's allinchapters 12--14"). Three dots ... will be converted to an ellipsis.Unicode is upported. ☺ </p>
    <span class="block text-sm mt-2 mb-2">Created by:Josh</span>
    <itme class="block text-sm text-blue-500"><span class="fas fa-clock"></span>2023-10-01</itme>
  </article>
</template>

<script>
export default {
  data() {
    return {
      post: {
        id: 1,
        title: "第一篇文章",
        content: "第一篇文章內容",
        content2: "第一篇文章內容2",
      },
    };
  },
};
</script>

<style></style>
