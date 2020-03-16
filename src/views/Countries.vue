<template>
  <div class="countries">
    {{title}}
  </div>
</template>


<script>
export default {
  name: 'Countries',
  props: [],
  data() {
    return {
      stats: [],
      title: 'Countries Stats',
    };
  },
  methods: {
    // async fetchData() {
    //   const response = await fetch('');
    //   const jsonData = await response.json();
    //   console.log(jsonData);
    // },
    async fetchCountries() {
      const response = await fetch('https://covid19.mathdro.id/api/countries');
      const jsonData = await response.json();
      // console.log(jsonData.iso3);
    },
  },
  created() {
    this.fetchCountries();
  },
};
</script>


<style scoped>
.countries {
  width: 90%;
  margin: 0 auto;
}
</style>
