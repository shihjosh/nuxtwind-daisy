<template>
  <div class=" min-h-screen bg-base-200">
    <div class="flex flex-col ml-3">
      <article class="prose md:prose-lg">
        <h1>{{ post.title }}</h1>
        <p>{{ post.content }}</p>
        <p>{{ post.content }}</p>
      </article>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      post: {
        id: 1,
        title: "第一篇文章",
        content:"第一篇文章內容",
      },
    };
  },
};
</script>

<style></style>
