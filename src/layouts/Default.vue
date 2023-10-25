<template>
  <div :data-theme="theme">
    <div class="navbar bg-base-100">
  <div class="flex-1">
    <a class="btn btn-ghost normal-case text-xl">Blog</a>
  </div>
  <div class="flex-none">
    <ul class="menu menu-horizontal px-1">
      <!-- <li><NuxtLink to="/">Home</NuxtLink></li> -->
      <li>
            <details>
              <summary>Posts</summary>
              <ul class="p-2 bg-base-100">
                <li v-for="post in posts" :key="post.id">
                  <NuxtLink :to="`/posts/${post.id}`">{{ post.title }}</NuxtLink>
                </li>
              </ul>
            </details>
          </li>
    </ul>
  </div>
  <div class="navba-end">
        <select
          v-model="theme"
          class="select select-primary md:w-auto"
        >
          <option disabled selected>Select Theme</option>
          <option v-for="theme in themes" :value="theme" :key="theme">
            <span class="uppercase">{{ theme }}</span>
          </option>
        </select>
      </div>
</div>
    <slot />
    <footer class="footer footer-center p-10 bg-base-50">
      <div>
        <h1 class="text-2xl md:text-3xl font-bold">Josh Where</h1>
        <!-- <p class="md:font-bold">
          Create beautiful and fast websites without the tedious setup
        </p> -->
        <p>Copyright © {{ new Date().getFullYear() }} - All right reserved</p>
      </div>
      <!-- <div>
        <div class="grid grid-flow-col gap-4">
          <a href="https://twitter.com/jrtiquez" target="_blank">
            <i class="lab la-twitter text-4xl"></i>
          </a>
          <a
            href="https://github.com/ossphilippines/nuxtwind-daisy"
            target="_blank"
          >
            <i class="lab la-github text-4xl"></i>
          </a>
          <a href="https://facebook.com/ossph.org" target="_blank">
            <i class="lab la-facebook text-4xl"></i>
          </a>
        </div>
      </div> -->
    </footer>
  </div>
</template>

<script>
import { ref, watch, onMounted } from "vue";
const THEMES = ["light", "dark", "wireframe"];
export default {
  data() {
    return {
      posts: [
        { id: 1, title: "第一篇文章" },
        { id: 2, title: "第二篇文章" },
        { id: 3, title: "第三篇文章" },
      ],
    };
  },
  setup() {
    const theme = ref(null);
    watch(theme, (value) => {
      localStorage.setItem("daisyui-theme", value);
    });
    onMounted(() => {
      theme.value = localStorage.getItem("daisyui-theme") || "dark";
    });
    return {
      theme,
      themes: THEMES,
    };
  },
};
</script>
