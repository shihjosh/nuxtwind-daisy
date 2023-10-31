<template>
  <generic-panel>
    <div class="container mx-auto grid place-content-center">
      <div v-if="review && review.attributes && review.attributes.body">
        <h1 class ="text-center text-4xl  md:text-5xl">{{ review.attributes.title }}</h1>
      <div
        class="prose-xl border border-gray-300 prose-blue text-black prose-pre:bg-zinc-300 prose-pre:text-gray-800 text-sm m-5 p-5 bg-gray-100 shadow-xl rounded-2xl"
        v-html="$mdRenderer.render(review.attributes.body)"
      />
    </div>
  </div>
  </generic-panel>
</template>

<script>
import GenericPanel from "~/components/commons/GenericPanel";

// 這裡要取得 ID 然後查詢資料
export default {
  components: {
    GenericPanel,
  },
  data() {
    return {
      markdown: "# Markdwon-it in Nuxt3",
      post: {
        id: 1,
        title: "第一篇文章 DEMO",
        content:
          "# An exhibit of Markdown\n\nThis note demonstrates some of what [Markdown][1] is capable of doing.\n\n*Note: Feel free to play with this page. Unlike regular notes, this doesn't automatically save itself.*\n\n## Basic formatting\n\nParagraphs can be written like so. A paragraph is the basic block of Markdown. A paragraph is what text will turn into when there is no reason it should become anything else.\n\nParagraphs must be separated by a blank line. Basic formatting of *italics* and **bold** is supported. This *can be **nested** like* so.\n\n## Lists\n\n### Ordered list\n\n1. Item 1\n2. A second item\n3. Number 3\n4. Ⅳ\n",
        author: "第一篇文章內容",
        created_at: "2023-10-15",
      },
      review:'',
    };
  }, 
  mounted() {
    // mounted 時，先取得一次資料
    this.checkPosts()
  },
  methods: {
   async checkPosts() {
    //根據取得的資料id 顯示
    const route = useRoute()
    const config = useRuntimeConfig()
    const id = route.params.id
    // console.log('route.params.id:',route.params.id)
    // console.log("baseurl:",config.public.apiBase)

    const postData = await $fetch(config.public.apiBase+'reviews/'+id)
    this.review = postData.data
  
  },
  },
};
</script>

<style></style>
