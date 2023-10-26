<template>
  <div class="min-h-screen bg-base-200">
    <div class="flex flex-row">
      <div class=" md:basis-1/4"></div>
      <div class=" ml-2 mt-3 md:container basis-2/4 mt-3 md:mx-auto">
        <div class="flex flex-col ml-3">
          <article class="prose md:prose-lg">
            <!-- <h1>{{ $route.params.id }}</h1> -->
            <h1>{{ post.title }}</h1>
            <p>{{ post.content }}</p>
            <p>{{ post.content2 }}</p>
          </article>
        </div>
      </div>
      <div class=" md:basis-1/4"></div>

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
        content: "第一篇文章內容",
        content2: "第一篇文章內容2",
      },
    };
  },
};
</script>

<style></style>
