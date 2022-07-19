<template>
  <div class="about">
    <p v-t="'message'"></p>
    <h1>This is an about page</h1>

    <component :is="currentArticlesComponent" />
  </div>
</template>

<script>
import Sample1Articles from "@/components/articles/sample1";
import Sample2Articles from "@/components/articles/sample2";

export default {
  name: "HelloI18n",
  components: {
    Sample1Articles,
    Sample2Articles
  },
  computed: {
    // 透過網址 /about?platform=sample1 來決定顯示哪個文章樣板
    currentArticlesComponent() {
      const {
        query: { platform }
      } = this.$route;

      switch (platform) {
        case "sample1":
          return Sample1Articles;
        case "sample2":
          return Sample2Articles;
        default:
          return false;
      }
    }
  }
};
</script>
