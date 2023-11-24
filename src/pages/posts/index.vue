<template>
  <generic-panel>
    <div>
      <h1 class="text-3xl mb-4">Latest Posts</h1>

      <section>
        <PostList v-for="post in reviews" :key="post.id" :post="post" />
      </section>

      <section>
        <div class="join">
          <button
            v-for="pageNumber in getVisiblePages"
            :key="pageNumber"
            :class="['join-item', 'btn', { 'btn-disabled': pageNumber === '...'}]"
            @click="goToPage(pageNumber)"
          >
            {{ pageNumber }}
          </button>
        </div>
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
      reviews: '',
      pagination: {
        page: 1, // 設定預設頁碼
        pageSize: 4,
        pageCount: 2,
        total: 5
      },
    };
  },
  mounted() {
    this.checkPosts();
  },
  computed: {
    getVisiblePages() {
      const visiblePages = [];
      const { page, pageCount } = this.pagination;

      for (let i = 1; i <= pageCount; i++) {
        if (i === page || i === page - 1 || i === page + 1 || i === 1 || i === pageCount) {
          visiblePages.push(i);
        } else if (i === page - 2 || i === page + 2) {
          visiblePages.push('...');
        }
      }

      return visiblePages;
    },
  },
  methods: {
    async checkPosts() {
      const config = useRuntimeConfig();
      const postData = await $fetch(`${config.public.apiBase}reviews?pagination[page]=${this.pagination.page}&pagination[pageSize]=${this.pagination.pageSize}&sort=id:desc`);
      this.reviews = postData.data;
      this.pagination = postData.meta.pagination;
      console.log('this.meta:', this.pagination);
      console.log('pageconta:', this.pagination.pageCount);
    },
    async goToPage(pageNumber) {
      const config = useRuntimeConfig();
      this.pagination.page = pageNumber;
      const postData = await $fetch(`${config.public.apiBase}reviews?pagination[page]=${pageNumber}&pagination[pageSize]=${this.pagination.pageSize}&sort=id:desc`);
      this.reviews = postData.data;
      this.pagination = postData.meta.pagination;
      console.log(`Go to page ${pageNumber}`);
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
