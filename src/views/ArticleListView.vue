<template>
  <main>
    <ArtcileFilter @keyword-search="filterSearch" />
    <h2>Article List</h2>
    <div class="article-list">
      <ArticleListItem
        v-for="article of articles"
        :key="article.title"
        :article="article"
      />
    </div>
  </main>
</template>

<script>
import ArticleListItem from "../components/ArticleListItem.vue";
import ArtcileFilter from "../components/ArticleFilter.vue";

export default {
  components: { ArticleListItem, ArtcileFilter },

  data() {
    return {
      // apiKey: "",
      q: "",
      headlines: "top-headlines",
      categories: "business",
      countries: "nz",
      articles: [],
    };
  },
  methods: {
    async fetchArticles() {
      // "https://vercel-backend-express-5finafhm3-alliedev.vercel.app",
      let response = await fetch("https://newsreader-app.vercel.app", {
        method: "POST",
        headers: {
          "Content-Type": "application/json",
        },
        body: JSON.stringify({
          headlines: this.headlines,
          country: this.countries,
          category: this.articles,
          query: this.q,
        }),
      });
      let data = await response.json();
      this.articles = data.articles;
    },

    filterSearch(searchString, headlines, categories, countries) {
      this.q = searchString;
      this.headlines = headlines;
      this.categories = categories;
      this.countries = countries;
      if (headlines !== "" && headlines === "everything") {
        if (this.q !== "") {
          this.fetchArticles();
        } else {
          alert("When selecting everything, you must provide keyword");
        }
      } else if (
        this.headlines !== "" &&
        headlines === "top-headlines" &&
        this.categories !== "" &&
        this.countries !== ""
      ) {
        this.fetchArticles();
      } else {
        alert("please fill in the inputs correctly");
      }
    },
  },
};
</script>

<style scoped>
main {
  padding: 0 2rem;
}

h2 {
  text-align: center;
  font-family: "Inter", sans-serif;
  text-decoration: underline;
}
.article-list {
  display: flex;
  flex-wrap: wrap;
}
</style>
