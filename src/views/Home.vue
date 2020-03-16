<template>
  <div class="home">
    <h3 class="title">Latest Stats</h3>
    <section v-if="!loading" class="info">
      <div class="card">Confirmed Cases {{stats.confirmed}}</div>
      <div class="card">Reported Deaths {{stats.deaths}}</div>
      <div class="card">Recoveries {{stats.recovered}}</div>
    </section>
    <section v-if="loading" class="loading">
      <div>Loading...</div>
    </section>
  </div>
</template>


<script>
export default {
  name: 'Home',
  props: [],
  data() {
    return {
      stats: {
        confirmed: null,
        deaths: null,
        recovered: null,
      },
      loading: false,
    };
  },
  methods: {
    async fetchData() {
      this.loading = true;
      const response = await fetch('https://covid19.mathdro.id/api');
      const jsonData = await response.json();
      const { confirmed, deaths, recovered } = jsonData;
      this.loading = false;
      this.stats.confirmed = confirmed.value;
      this.stats.deaths = deaths.value;
      this.stats.recovered = recovered.value;
    },
  },
  created() {
    this.fetchData();
  },
};
</script>


<style scoped>
.home {
  width: 90%;
  margin: 0 auto;
}

.title {
  font-size: 1.5rem;
  font-weight: 300;
}

.info {
  width: 100%;
  padding: 1rem 0;
}

.card {
  border: 1px solid #eee;
  padding: 1rem;
  margin-bottom: 1rem;
  font-size: 1.25rem;
}

.loading {
  text-align: left;
  font-size: 1.25rem;
}

@media screen and (min-width: 860px) {
  .info {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
  }

  .card {
    margin-right: 1rem;
  }
}
</style>
