<template>
  <div class="headlines">
    <label for="headlines">Headlines</label>
    <select v-model="headlines" id="headlines">
      <option value="top-headlines">Top Headlines</option>
      <option value="everything">Everything</option>
    </select>
    <label for="categories">Categories</label>
    <select v-model="selectedCategory" id="categories">
      <option
        v-for="category of categoryList"
        :key="category"
        :value="category"
      >
        {{ category }}
      </option>
    </select>
    <label for="countries">Countries</label>
    <select v-model="selectedCountry" id="countries">
      <option v-for="country of countryList" :key="country" :value="country">
        {{ country }}
      </option>
    </select>
  </div>
  <div class="input-search">
    <label for="search-string">Keyword Search</label>
    <input v-model="userInput" type="text" id="search-string" />
    <button @click="emitSearchEvent">Search</button>
  </div>
</template>

<script>
export default {
  name: "ArticleFilter",
  emits: ["keywordSearch"],
  data() {
    return {
      userInput: "",
      headlines: "",
      selectedCategory: "",
      selectedCountry: "",
      categoryList: [
        "business",
        "entertainment",
        "general",
        "health",
        "science",
        "sports",
        "technology",
      ],
      countryList: [
        "ae",
        "ar",
        "at",
        "au",
        "be",
        "bg",
        "br",
        "ca",
        "ch",
        "cn",
        "co",
        "cu",
        "cz",
        "de",
        "eg",
        "fr",
        "gb",
        "gr",
        "hk",
        "hu",
        "id",
        "ie",
        "il",
        "in",
        "it",
        "jp",
        "kr",
        "lt",
        "lv",
        "ma",
        "mx",
        "my",
        "ng",
        "nl",
        "no",
        "nz",
        "ph",
        "pl",
        "pt",
        "ro",
        "rs",
        "ru",
        "sa",
        "se",
        "sg",
        "si",
        "sk",
        "th",
        "tr",
        "tw",
        "ua",
        "us",
        "ve",
        "za",
      ],
    };
  },
  methods: {
    emitSearchEvent() {
      this.$emit(
        "keyword-search",

        this.userInput,
        this.headlines,
        this.selectedCategory,
        this.selectedCountry
      );
    },
  },
};
</script>

<style scoped>
.headlines {
  padding: 0 0 2rem 0;
  font-family: "Inter", sans-serif;
  display: flex;
  justify-content: center;
}

select {
  background-color: #faf5ed;
  border: 1px solid;
  border-radius: 5px;
}

.input-search {
  padding: 0 0 2rem 0;
  font-family: "Inter", sans-serif;
  display: flex;
  justify-content: center;
}

label {
  padding: 0 1rem;
  color: grey;
  font-family: 'Courier New', Courier, monospace;
}

input {
  background-color: #faf5ed;
  border: 1px solid;
  border-radius: 5px;
}

button {
  margin: 0 1rem;
  border-radius: 5px;
  font-family: "Inter", sans-serif;
  background-color: #faf5ed;
  border: 1px solid;
  cursor: pointer;
}
</style>
