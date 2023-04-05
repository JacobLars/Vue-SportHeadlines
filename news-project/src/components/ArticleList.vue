<template>
    <div>
      
      <ul>
        <li v-for="(article) in articles" :key="article.url">
          <Article :article="article" />
        </li>
      </ul>
    </div>
  </template>
  
  <script>
  
  import Article from './Article.vue';
  
  export default {
    components: {
      Article,
    },
    props: {
      articles: {
        type: Array,
        required: true,
      },
    },
  };
  </script>