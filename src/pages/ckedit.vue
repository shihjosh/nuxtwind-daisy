<template>

        <div v-if="review && review.attributes && review.attributes.body">
        
          <div v-html="review.attributes.body"></div>
      </div>

  </template>


  <script>
  import GenericPanel from "~/components/commons/GenericPanel";
  
  // 這裡要取得 ID 然後查詢資料
  export default {
    layout: "nolayouts",
    components: {
      GenericPanel,
    },
    data() {
      return {
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
      //const route = useRoute()
      const config = useRuntimeConfig()
      //const id = route.params.id
      // console.log('route.params.id:',route.params.id)
      // console.log("baseurl:",config.public.apiBase)
  
      const postData = await $fetch(config.public.apiBase+'ckedits/1')
      this.review = postData.data
    
    },
    },
  };
  </script>
  
  <style>

  </style>
  