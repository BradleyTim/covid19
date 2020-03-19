<template>
  <div id="app">
    <Header></Header>
    <router-view :key="$route.path"/>
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
  --success: #5cb85c;
  --danger: #bf3f3f;
  --warning: yellow;
  --default: #777;
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
  margin-top: 5rem;
  margin-bottom: 5rem;
}

.text-danger {
  color: var(--danger);
}

.text-warning {
  color: var(--warning);
}

.text-default {
  color: var(--default);
}
.text-success {
  color: var(--success);
}

.bg-default {
  border-color: #ccc;
  background: #eee;
}

.bg-danger {
  border-color: #f55872;
  background: #f8d7da;
}

.bg-success {
  border-color: #66d16e;
  background: #d4edda;
}
</style>
