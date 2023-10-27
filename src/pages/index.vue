<template>
  <div class="hero min-h-screen bg-base-200" style="background-image: url('/a01.jpg')">
    <div class="hero-content text-center" >
      <div class="max-w-xl">
        <h1 data-aos="fade-down" class="text-4xl text-zinc-900 md:text-7xl text-zinc-900 font-bold mb-6">
          Josh Where 不做永遠是 0%
        </h1>
        <p data-aos="fade-down" data-aos-delay="300" class="md:text-lg text-zinc-900 mb-6">
          這是我的部落~施工中~~!
        </p>
        <div class="flex justify-center space-x-5">
          <a
            data-aos="fade-down"
            data-aos-delay="600"
            class="btn btn-sm md:btn-md btn-primary"
            href="https://github.com/"
            target="_blank"
          >
            Git Hub 連結
          </a>
          <a
            data-aos="fade-down"
            data-aos-delay="600"
            class="btn btn-sm md:btn-md btn-primary"
            href="https://tw.yahoo.com/"
            target="_blank"
          >
            Yahoo~! 奇摩~!
          </a>
        </div>
      </div>
    </div>
  </div>
  <div class="grid grid-cols-1 md:grid-cols-3 gap-3 mt-6 ml-3">

  
    <div v-for="post in posts" :key="post.id"  data-aos="fade-up" class="card w-96 bg-base-100 shadow-xl image-full">
        <figure>
          <img :src="post.image" :alt="post.title" />
        </figure>
        <div class="card-body">
          <h2 class="card-title">{{ post.title }}</h2>
          <p>{{ post.content }}</p>
          <div class="card-actions justify-end">
            <button class="btn btn-primary">GO!</button>
          </div>
        </div>
      </div>

    </div>
</template>

<script>
export default {
  data() {
    return {
      posts: [
        { id: 1, title: "第一篇文章",content:"content 第一篇文章",image:"https://daisyui.com/images/stock/photo-1606107557195-0e29a4b5b4aa.jpg" },
        { id: 2, title: "第二篇文章",content:"content 第二篇文章",image:"https://daisyui.com/images/stock/photo-1606107557195-0e29a4b5b4aa.jpg" },
        { id: 3, title: "第三篇文章",content:"content 第三篇文章",image:"https://daisyui.com/images/stock/photo-1606107557195-0e29a4b5b4aa.jpg" },
        { id: 4, title: "第四篇文章",content:"content 第四篇文章",image:"https://daisyui.com/images/stock/photo-1606107557195-0e29a4b5b4aa.jpg" },
        { id: 5, title: "第四篇文章",content:"content 第四篇文章",image:"https://daisyui.com/images/stock/photo-1606107557195-0e29a4b5b4aa.jpg" },
      ],
    };
  },
};
</script>
