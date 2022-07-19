<i18n src="./i18n.json"></i18n>
<i18n lang="json">
{
  "en": {
    "title": "Sample1Articles",
    "articleList": {
      "article1": {
        "title": "sample1 article1",
        "list": [
          "list 1 list 1 list 1 list 1 list 1 ",
          "list 2 list 2 list 2 list 2 list 2 list 2 ",
          "list 3 list 3 list 3 list 3 list 3"
        ]
      },
      "article2": {
        "title": "sample1 article2",
        "list": [
          "list 1 list 1 list 1 list 1 list 1 ",
          "list 2 list 2 list 2 list 2 list 2 list 2 ",
          "list 3 list 3 list 3 list 3 list 3"
        ]
      }
    }
  },
  "zh": {
    "title": "Sample1Articles",
    "articleList": {
      "article1": {
        "title": "sample1 文章1",
        "list": [
          "文章段落 1 文章段落 1 文章段落 1 文章段落 1 文章段落 1 ",
          "文章段落 2 文章段落 2 文章段落 2 文章段落 2 文章段落 2 文章段落 2 ",
          "文章段落 2 文章段落 2 文章段落 2 文章段落 2 文章段落 2 文章段落 2 "
        ]
      }
    }
  }
}
</i18n>
<template>
  <div>
    <!-- 文章列表 -->
    <div class="articles">
      <div
        class="articles__item"
        v-for="(article, articleKey) in $t('articleList')"
        :key="articleKey"
      >
        <h1 v-t="`articleList.${articleKey}.title`" />
        <ul>
          <template
            v-for="(list, listKey) in $t(`articleList.${articleKey}.list`)"
          >
            <li v-t="`articleList.${articleKey}.list[${listKey}]`" />
          </template>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Sample1Articles"
};
</script>

<style lang="scss" scoped></style>
