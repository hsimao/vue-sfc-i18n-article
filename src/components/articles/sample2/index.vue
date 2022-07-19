<i18n src="./i18n.json"></i18n>
<i18n lang="json">
{
  "hello": "123"
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
  name: "Sample2Articles"
};
</script>

<style lang="scss" scoped></style>
