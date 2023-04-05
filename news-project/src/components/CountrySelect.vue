<template>
    <div class="select-container">
        <label for="country-select">Select a country:</label>
        <select id="country-select" v-model="selectedCountry" @change="fetchArticles">
            <option v-for="country in countries" :key="country.code" :value="country.code">{{ country.name }}</option>
        </select>
    </div>
</template>
  
<script>

export default {
    data() {
        return {
            selectedCountry: 'us',
            countries: [
                { code: 'at', name: 'Austria'},
                { code: 'be', name: 'Belgium' },
                { code: 'br', name: 'Brasil' },
                { code: 'ca', name: 'Canada' },
                { code: 'co', name: 'Colombia' },
                { code: 'de', name: 'Germany' },
                { code: 'gb', name: 'United Kingdom' },
                { code: 'kr', name: 'South Korea' },
                { code: 'mx', name: 'Mexico' },
                { code: 'no', name: 'Norway' },
                { code: 'se', name: 'Sweden' },
                { code: 'sg', name: 'Singapore' },
                { code: 'th', name: 'Thailand' },
                { code: 'us', name: 'United States' },
                { code: 'au', name: 'Australia' }
            ],
        };
    },
    methods: {
        fetchArticles() {
            this.$emit('fetch-articles', this.selectedCountry);
        },
    },
};
</script>