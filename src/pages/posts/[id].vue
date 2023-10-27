<template>
  <article class="card mb-7 mt-1">
    <h1 class="text-3xl mb-2 text-center">{{ post.title }}</h1>
    <p >{{ post.content }}</p>
    <span class="block text-sm mt-2 mb-2">Created by:{{ post.author }}</span>
    <itme class="block text-sm text-blue-500"><span class="fas fa-clock"></span>{{ post.created_at }}</itme>
  </article>
</template>

<script>
// const route = useRoute();
// 這裡要取得 ID 然後查詢資料
export default {
  data() {
    return {
      post: {
        id: 1,
        title: "第一篇文章 DEMO",
        content: "美中關係持續緊張，近日經常互控對方挑釁，美軍26日發布聲明並公布影片指，一架中國戰機在南海空域對美國空軍B-52轟炸機進行不安全的攔截動作，雙方相距10英尺（約3公尺）。美國印太司令部26日發布聲明說，本月24日一架中國戰機對一架美國空軍飛機進行了「不安全」的攔截，稱該名中國飛行員以「不安全和不專業」的方式飛行，且不控的超速貼近，在距離B-52的機身前方和下方不到10英尺（約3公尺）飛過，表現出糟糕的飛行素養，讓兩機有相撞危險。",
        author: "第一篇文章內容",
        created_at: "2023-10-15",
      },
    };
  },
};
</script>

<style></style>
