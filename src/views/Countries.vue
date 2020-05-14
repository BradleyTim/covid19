<template>
  <div class="countries">
    <h3 class="title">{{title}}</h3>
    <section class="countries-container">
      <!-- <form>
        <input
          type="text"
          class="search-input"
          placeholder="Search your Country"
          v-model="country"
          @change="searchCountry(country)"
        >
      </form> -->
      <div v-if="!loading">
        <!-- form here -->
        <Search />
        <div class="card bg-default"  v-for="(info, index) in stats" :key="index">
          <h3 class="country-name">{{info.country}}</h3>
          <!-- <p v-if="info.provinceState" class="state">
            Province/State: {{info.provinceState}}
          </p> -->
          <p class="confirmed">Confirmed Cases: <span class="">{{info.cases}}</span></p>
          <p class="recovered">Recorvered: <span class="text-success">{{info.recovered}}</span></p>
          <p class="deaths">Deaths: <span class="text-danger">{{info.deaths}}</span></p>
        </div>
      </div>
      <div class="loading" v-if="loading">
        <img src="@/assets/Spinner-1s-200px.svg" alt="loading spinner">
      </div>
    </section>
  </div>
</template>


<script>
export default {
  name: 'Countries',
  props: [],
  data() {
    return {
      stats: null,
      title: 'Countries Statistics',
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
    async searchCountry(country) {
      const x = this.stats.filter((stat) => stat.country.toLowerCase() === country.toLowerCase());
      console.log(x);
      return x;
    },
  },
  created() {
    this.fetchData();
  },
};
</script>


<style scoped>
.countries {
  width: 90%;
  margin: 0 auto;
  z-index: -1;
}

.title {
  font-weight: 300;
  font-size: 1.5rem;
  text-align: center;
}

.countries-container {
  margin-top: 1rem;
}

.card {
  border: 1px solid #eee;
  border-radius: 3px;
  padding: 1rem;
  margin-bottom: 1rem;
}

.loading {
  text-align: center;
}

p {
  margin: .25rem 0;
  font-size: 1.15rem;
}

/* form styles */
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
  border-color: #2c3e50;
}
</style>
