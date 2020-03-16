<template>
  <header>
    <nav>
      <h2 class="brand-name">
        <router-link to="/">
            <a>COVID-19</a>
          </router-link>
      </h2>
      <ul class="menu">
        <li class="menu-item">
          <router-link to="/">
            <a>Home</a>
          </router-link>
        </li>
        <li class="menu-item">
          <router-link to="/countries">
            <a>Countries</a>
          </router-link>
        </li>
        <li class="menu-item">
          <router-link to="/about">
            About
          </router-link>
        </li>
      </ul>
    </nav>
  </header>
</template>

<script>
export default {
  name: 'Header',
};
</script>


<style scoped>
header {
  width: 100%;
  background: #fff;
  border-bottom: 1px solid #eee;
  /* box-shadow: 0 0 2px #eee; */
  margin-bottom: 1rem;
}

nav {
  width: 90%;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.brand-name {
  color: #2c3e50 !important;
  font-size: 1.5rem;
  letter-spacing: 2px;
}

.menu {
  display: flex;
  justify-content: space-between;
  list-style: none;
}

.menu-item {
  padding-left: 1rem;
  font-size: 1rem;
}

a {
  color: #777;
  text-decoration: none;
}
</style>
