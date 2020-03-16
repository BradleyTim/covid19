<template>
  <div class="countries">
    <h3 class="title">{{title}}</h3>
    <section class="countries-container">
      <div v-if="!loading">
        <div class="card"  v-for="(info, index) in stats" :key="index">
        <h3 class="country-name">{{info.countryRegion}}</h3>
        <p class="state">Province/State: {{info.provinceState}}</p>
        <p class="confirmed">Confirmed Cases: {{info.confirmed}}</p>
        <p class="recovered">Recorvered: {{info.recovered}}</p>
        <p class="deaths">Deaths: {{info.deaths}}</p>
      </div>
      </div>
      <div class="loading" v-if="loading">
        <p>Loading...</p>
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
      loading: false,
    };
  },
  methods: {
    async fetchData() {
      this.loading = true;
      const response = await fetch('https://covid19.mathdro.id/api/confirmed');
      const jsonData = await response.json();
      this.loading = false;
      this.stats = jsonData;
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
</style>
