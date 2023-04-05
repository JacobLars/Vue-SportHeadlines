
<template>
  
  <sportheader></sportheader>
  <div  class="main-container">
    <h2 id="articles_title">Articles</h2>
    <countrySelect @fetch-articles="fetchArticles" />
    <articleList :articles="articles" />
  </div>

</template>

<script>
import axios from 'axios';
import sportheader from './components/SportsHeader.vue';
import countrySelect from './components/CountrySelect.vue';
import articleList from './components/ArticleList.vue';



export default {
  components: {
    sportheader,
    countrySelect,
    articleList,
   
  },
  data() {
    return {
      articles: [],
    };
  },
  methods: {
    async fetchArticles(selectedCountry) {
      const response = await axios.get(`https://newsapi.org/v2/top-headlines?country=${selectedCountry}&category=sports&apiKey=56c7d771df744ae6a876046c137620a3`);
      this.articles = response.data.articles;
    },
  },
};

</script>

<style scoped></style>

