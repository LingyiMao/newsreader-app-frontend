<template>
  <div class="article-list__card">
    <img :src="article.urlToImage" />
    <h3>{{ article.title }}</h3>
    <p>{{ article.description }}</p>
    <h4 v-if="article.author !== null">Author:{{ article.author }}</h4>
    <h4 v-else>Author: Unknown</h4>
  </div>
</template>

<script>
export default {
  props: {
    article: Object,
  },
};
</script>

<style scoped>
.article-list__card {
  width: 300px;
  height: 500px;
  padding: 1.8em;
  border-bottom: 1px solid gray;
  box-shadow: 5px 0 15px -15px gray;
}

img {
  width: 300px;
}

h3 {
  font-family: "Newsreader", serif;
}

p {
  font-family: "Roboto", sans-serif;
  font-weight: 100;
}

h4 {
  font-family: "Roboto", sans-serif;
  font-weight: 500;
}
</style>
