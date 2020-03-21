<template>
  <div class="home">
    <h3 class="title">Latest Statistics</h3>
    <section v-if="!loading">
      <div class="info">
        <div class="card bg-default text-default">
          Confirmed Cases <span class="">{{stats.confirmed}}</span>
        </div>
        <div class="card bg-danger text-danger">
          Reported Deaths <span class="">{{stats.deaths}}</span>
        </div>
        <div class="card bg-success text-success">
          Recoveries <span class="">{{stats.recovered}}</span>
        </div>
      </div>
      <stay-safe></stay-safe>
    </section>
    <section v-if="loading" class="loading">
        <img src="@/assets/Spinner-1s-200px.svg" alt="loading spinner">
    </section>
  </div>
</template>


<script>
import StaySafe from '@/components/StaySafe.vue';

export default {
  name: 'Home',
  components: {
    StaySafe,
  },
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
  font-size: 1.35rem;
  font-weight: 300;
  text-align: center;
}

.info {
  width: 100%;
  padding: 1rem 0;
}

.card {
  border-radius: 3px;
  padding: 1rem;
  margin-bottom: 1rem;
  font-size: 1.25rem;
  text-align: center;
}

@media screen and (min-width: 860px) {
  .home {
    margin: 1rem auto;
  }

  .title {
    font-size: 1.5rem;
    margin-bottom: 1rem;
  }

  .info {
    padding: 1rem 0 5rem 0;
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-gap: 1rem;
  }
}
</style>
