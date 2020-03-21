<template>
  <div id="app">
    <Header></Header>
    <transition name="slide-fade" mode="out-in">
      <router-view :key="$route.path"/>
    </transition>
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

  min-height: 90vh;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
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

.loading {
  text-align: center;
}

.loading img {
  width: 125px;
}

/* .fade-enter-active, .fade-leave-active {
  transition: opacity .4s;
}
.fade-enter, .fade-leave-to {
  opacity: 0;
} */


/* Enter and leave animations can use different */
/* durations and timing functions.              */
.slide-fade-enter-active {
  transition: all .3s ease;
}
.slide-fade-leave-active {
  transition: all .3s cubic-bezier(1.0, 0.5, 0.8, 1.0);
}
.slide-fade-enter, .slide-fade-leave-to
/* .slide-fade-leave-active below version 2.1.8 */ {
  transform: translateX(10px);
  opacity: 0;
}
</style>
