<template>
  <div class="notfound">
    <div class="notfound-info">
      <h3>404 | NOT FOUND</h3>
      <div>
        Ooops! We couldn't find that page...try going to
         <router-link to="/">home</router-link> page.
      </div>
    </div>
  </div>
</template>


<style scoped>
.notfound {
  width: 90%;
  margin: 0 auto;
}

.notfound-info {
  margin-top: 5rem;
  font-size: 1.25rem;
  border: 1px solid #eee;
  box-shadow: 3px 5px 0 0#eee;
  padding: 2rem;
}

h3 {
  font-weight: 300;
  text-align: center;
  margin-bottom: 1rem;
}

div {
  text-align: center;
}

@media screen and (max-width: 500px) {
  .notfound-info {
    margin-top: 2rem;
    font-size: 1.25rem;
    padding: 1rem;
    border: none;
    box-shadow: none;
    text-align: center;
  }
}
</style>
