<template>
  <div class="hero min-h-screen bg-base-200">
    <div class="flex flex-col text-center">
      <h1 class="text-3xl md:text-5xl mb-5">{{ post.title }}</h1>
      <p class="md:text-lg">{{ post.content }}</p>
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
        content: "這是第一篇文章的內容。",
      },
    };
  },
};
</script>

<style></style>
