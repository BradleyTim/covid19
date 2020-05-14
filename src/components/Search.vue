<template>
  <section class="search-page">
    <form>
      <input
        type="text"
        class="search-input"
        placeholder="Search your Country"
        v-model="country"
        @change="searchCountry($event)"
      >
    </form>
    <div class="results">
      Results here
    </div>
  </section>
</template>

<script>
export default {
  name: 'Search',
  data() {
    return {
      stats: null,
      country: '',
      loading: false,
    };
  },
  methods: {
    async fetchData() {
      this.loading = true;
      const API_URL = process.env.VUE_APP_API_URL_COUNTRIES;
      const response = await fetch(API_URL);
      const jsonData = await response.json();
      this.loading = false;
      this.stats = jsonData;
    },
    async searchCountry(event) {
      event.preventDefault();
      const data = this.stats.maps((stat) => {
        if (stat.country.toLowerCase() === this.country.toLowerCase()) {
          return stat;
        }
        return 'nada';
      });
      console.log(data);
      return data;
    },
  },
  created() {
    this.fetchData();
  },
};
</script>

<style scoped>
.search-page {
  width: 90%;
  margin: 0 auto;
}

form {
  margin: 1rem 0;
  width: 100%;
}

input.search-input {
  display: block;
  width: 100%;
  padding: .5rem;
  font-size: 1.15rem;
  color: #888;
  border: 1px solid #2c3e50;
  border-radius: 3px;
}

input:focus {
  border-color: var(--success);
  outline: none;
}
</style>
