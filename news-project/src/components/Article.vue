<template>
    <div class="news-container">
        <h3 class="news-title"><a :href="article.url">{{ article.title }}</a></h3>
        <p class="news-decription">{{ article.description }}</p>
        <img class="news-image" :src="articleImage" :alt="article.title" />
        <p class="news-publish">Published at: {{formatDate(article.publishedAt)}}</p>
        <p>Source: {{ article.source.name }}</p>
    </div>
</template>
  
<script>

import noImage from '@/assets/noimage.jpg';
export default {
    props: {
        article: {
            type: Object,
            required: true,
        },
    },
    methods: {
    formatDate(dateString) {
      const date = new Date(dateString);
      return date.toLocaleString();
    }
  },
    computed: {
        articleImage() {
            return this.article.urlToImage ? this.article.urlToImage : noImage;
        }
    }
};
</script>