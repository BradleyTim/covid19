<template>
  <header>
    <nav>
      <h2 class="brand-name">
        <router-link to="/">
            <a>COVID19</a>
          </router-link>
      </h2>
      <ul class="menu">
        <li class="menu-item">
          <router-link to="/countries">
            <a>Countries</a>
          </router-link>
        </li>
        <li class="menu-item">
          <router-link to="/Search">
            <a>Search</a>
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
  background: #2c3e50;
  padding: 1rem 0;
  /* margin-bottom: 2rem; */
  box-shadow: 0 5px 3px 0 #eee;
  position: fixed;
  top: 0;
  right: 0;
  z-index: 5;
}

nav {
  width: 90%;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.brand-name {
  flex: 2;
  font-size: 1.45rem;
  font-weight: 900;
  letter-spacing: 2px;
}

.brand-name a {
  color: #eee;
}

.menu {
  flex: 1;
  display: flex;
  justify-content: flex-end;
  list-style: none;
}

.menu-item {
  padding-left: .85rem;
  font-size: 1.05rem;
  font-weight: 300;
}

a {
  color: #eee;
  text-decoration: none;
}
</style>
