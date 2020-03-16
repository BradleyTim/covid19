<template>
  <div id="app">
    <Header></Header>
    <router-view/>
    <Footer></Footer>
  </div>
</template>


<script>
import Header from '@/components/Header.vue';
import Footer from '@/components/Footer.vue';

export default {
  name: 'Home',
  components: {
    Header,
    Footer,
  },
};
</script>


<style>
:root {
  --success: green;
  --danger: red;
  --warning: yellow;
}

* {
  padding: 0;
  margin: 0;
  position: relative;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 7rem;
  margin-bottom: 5rem;
}

.text-danger {
  color: var(--danger);
}

.text-warning {
  color: var(--warning);
}
.text-success {
  color: var(--success);
}
</style>
