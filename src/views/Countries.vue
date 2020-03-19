<template>
  <div class="countries">
    <h3 class="title">{{title}}</h3>
    <section class="countries-container">
      <div v-if="!loading">
        <div class="card bg-default"  v-for="(info, index) in stats" :key="index">
          <h3 class="country-name">{{info.countryRegion}}</h3>
          <p v-if="info.provinceState" class="state">Province/State: {{info.provinceState}}</p>
          <p class="confirmed">Confirmed Cases: <span class="">{{info.confirmed}}</span></p>
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
</style>
