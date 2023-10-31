<template>
  <generic-panel>
  <div>
    <h1 class="text-3xl mb-4">Latest Posts</h1>

    <section>
      <PostList v-for="post in reviews" :key="post.id" :post="post" />
    </section>
  </div>
</generic-panel>
</template>

<script>
import GenericPanel from "~/components/commons/GenericPanel";
import PostList from "~/components/commons/PostList";
export default {
  components: {
    GenericPanel,
    PostList,
  },
  data() {
    return {
      posts: [
        {
          id: 1,
          title: "第一篇文章",
          content:
            "美中關係持續緊張，近日經常互控對方挑釁，美軍26日發布聲明並公布影片指，一架中國戰機在南海空域對美國空軍B-52轟炸機進行不安全的攔截動作，雙方相距10英尺（約3公尺）。美國印太司令部26日發布聲明說，本月24日一架中國戰機對一架美國空軍飛機進行了「不安全」的攔截，稱該名中國飛行員以「不安全和不專業」的方式飛行，且不控的超速貼近，在距離B-52的機身前方和下方不到10英尺（約3公尺）飛過，表現出糟糕的飛行素養，讓兩機有相撞危險。",
          author: "第一篇文章內容",
          created_at: "2023-10-15",
        },
        {
          id: 2,
          title: "第2篇文章",
          content:
            "印太司令部也指出，該次攔截在「能見度有限」的夜間進行，並控中國的攔截方式違背國際飛行安全規則與規範，印太司令部強調軍用飛機在有意彼此靠近時，應以專業的飛行技術操作，並對另一架飛機的安全予以適當考慮。中國做出最新挑釁行為之際，預計美國總統拜登將於當地時間27日在白宮與中國外交部長王毅會談。目前尚不清楚這次會晤是正面會談還是偏非正式的會面語問候。王毅預計當地時間26日會見美國務卿布林肯、27日會見國家安全顧問蘇利文。",
          author: "第2篇文章內容2",
          created_at: "2023-10-01",
        },
      ],
      reviews:'',
    };
  }, 
  mounted() {
    // // mounted 時，先取得一次資料
    this.checkPosts()
  },
  methods: {
   async checkPosts() {
    const config = useRuntimeConfig()
    // console.log("baseurl:",config.public.apiBase)
    const postData = await $fetch(config.public.apiBase+'reviews')
    this.reviews = postData.data
  },
  },
};
</script>

<style lang="css" scoped>
h1,
h2,
h3,
h4,
h5,
h6 {
  @apply text-gray-500;
}
</style>
